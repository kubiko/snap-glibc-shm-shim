# snap-glibc-shm-shim
glibs snap shim to redirect used sharem memory into snap permited sub dir
use SNAP_SHM_SUB_DIR
  include in your environment:
  SNAP_SHM_SUB_DIR="snap.${SNAP_NAME}."

alternatively add prefix for file created under /dev/shm/snap.<snap-name>.XXXXXX
by using SNAP_SHM_PREFIX
  include in your environment:
  SNAP_SHM_PREFIX="snap.${SNAP_NAME}."
