## Graphia Pro

  - Open JDK 7
  - Maven
  - sign4j
  - osslsigncode
  - NSIS

## GraphTool

  - g++
  - libgl1-mesa-dev
  - cppcheck
  - doxygen (and graphviz)
  - Clang on linux
      - clang, libxcb-xinerama0-dev
      - build-dep qt5-default
      - configure -opensource -confirm-license -prefix
        /var/lib/jenkins/Qt/<destination-dir> -platform linux-clang -gtk
        \[-no-use-gold-linker until QTBUG-66571 is addressed\]

## Code signing

In order to create or renew the certificates, use the Thawte interface
from the renewal email and choose the Microsoft code signing option.
Generate a CSR using the DigiCert Certificate Utility for Windows, on
the build server itself. Wait a few days, exchange emails, phone calls
and vast amounts of money. Once the certificate is emailed to you,
import it into DigiCert Certificate Utility, which can then search for
and export the private key (stored on the build server in a mysterious
place). Convert the exported pfx/pkcs12 file to pem format using
`openssl pkcs12 -in exported-private-key.pfx -out
exported-private-key.pem`. Using the script below, create the p12
keystore from the certificate and private key (in PEM format). Copy the
newly created p12 keystore to the build server.

`#! /bin/bash`
`     `
` CERT_FILE=$1`
` PRIVATE_KEY=$2`
` PASSWORD=$3`
`     `
` if [ $# -lt 3 ]`
` then`
`   echo "Usage: $0 CERTIFICATE PRIVATEKEY PASSWORD"`
`   exit 1`
` fi`
`    `
` if [ ! -f "${CERT_FILE}" ]`
` then`
`   echo "${CERT_FILE} doesn't exist"`
`   exit 1`
` fi`
`     `
` if [ ! -f "${PRIVATE_KEY}" ]`
` then`
`   echo "${PRIVATE_KEY} doesn't exist"`
`   exit 1`
` fi`
`     `
` if [ -z "${PASSWORD}" ]`
` then`
`   echo "No password supplied"`
`   exit 1`
` fi`
`     `
` rm -f kajeka-p12-keystore.p12 kajeka-java-keystore.jks`
`     `
` openssl pkcs12 -export -out kajeka-p12-keystore.p12 \`
`   -passin pass:${PASSWORD} \`
`   -password pass:${PASSWORD} \`
`   -inkey ${PRIVATE_KEY} -in ${CERT_FILE} && \`
` keytool -importkeystore -noprompt \`
`   -srckeystore kajeka-p12-keystore.p12 -srcstoretype pkcs12 \`
`   -srcstorepass ${PASSWORD} -srcalias 1 \`
`   -destkeystore kajeka-java-keystore.jks -deststoretype jks \`
`   -deststorepass ${PASSWORD} -destalias kajeka`