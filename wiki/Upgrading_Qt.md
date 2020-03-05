# Windows

  - Install Qt to C:\\sdks\\Qt\\Qt5.x
  - Edit PATH in C:\\Jenkins\\environment.bat

# OSX

  - Install Qt to /sdks/Qt5.x
  - Edit PATH and LD_LIBRARY_PATH in
    /Users/jenkins/home/environment.sh

# Linux

  - Install Qt to /var/lib/jenkins/Qt/5.x
  - Edit PATH and LD_LIBRARY_PATH in /var/lib/jenkins/environment.sh
  - Build (with clang) from source and install to
    /var/lib/jenkins/Qt/5.x-clang
  - Edit PATH and LD_LIBRARY_PATH in
    /var/lib/jenkins/environment-clang.sh