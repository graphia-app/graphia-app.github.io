## Cloning VMWare ESXI

  - Install ESXI 6.5.0 a
  - Open web UI
  - Add license 1N432-0U007-Q8880-0U28M-19DMK
  - Create VMs (without disks)
  - Enable SSH
  - From shell, clone images from old datastore to new datastore:

` $ vmkfstools -d thin -i /vmfs/volumes/[old...]/Linux/Linux.vmdk /vmfs/volumes/[new...]/Linux/Linux.vmdk`

  - Add images to newly created VMs
  - Update MAC addresses on the DHCP server (don't try to change the
    individual VM addresses to match the existing configuration)
  - Get DrDonk-unlocker-v209 and run esxi-install.sh (otherwise Mac OS
    won't boot)