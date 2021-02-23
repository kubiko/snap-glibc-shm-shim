# snap-glibc-shm-shim
glibc snap shim to redirect used sharem memory into snap permited path

use `SNAP_SHM_SUB_DIR` or `SNAP_SHM_PREFIX` evn variable to control functionality.  
  `SNAP_SHM_SUB_DIR` will use sub dir under `/dev/shm` eg. `/dev/shm/snap.<snap-name>./*`  
  `SNAP_SHM_PREFIX` adds prefix to the file name eg `/dev/shm/snap.<snap-name>.*`

include either of the env variables in your snap environment:  
  `SNAP_SHM_SUB_DIR="snap.${SNAP_NAME}."`  
  `SNAP_SHM_PREFIX="snap.${SNAP_NAME}."`

snapcraft.yaml example
```
environment:
    SNAP_SHM_PREFIX: "snap.${SNAP_NAME}."

parts:
    libc-shm-shim:
        plugin: nil
        stage-snaps:
            - libc-shm-shim/18/beta
```
