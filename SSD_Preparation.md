Wipe and Prepare Second SSD
   
        Identify Second SSD:
            Navigate to Node > Disks.
            Identify the second SSD (e.g., /dev/sdb).
        Wipe Second SSD:
            Click Wipe and confirm.
        Create New GPT Partition Table:
            Click Initialize Disk with GPT.
        Create ZFS Pool:
            Navigate to Node > Disks > ZFS.
            Click Create ZFS.
            Name pool (e.g., mainPool).
            Select second SSD and choose RAID0.
        Configure Proxmox Storage:
            Navigate to Datacenter > Storage.
            Click Add > ZFS.
            Configure ID and select ZFS pool.
        Verify Storage Configuration:
            Check storage under Node > Summary


Unmounting SSD
: umount /dev/nvme0n1p1

Checking for open files
: lsof | grep /dev/nvme0n1p1

Manually wiping SSD
: dd if=/dev/zero of=/dev/nvme0n1 bs=1M status=progress
