Create a VM on the same SSD as Proxmox and use the second SSD as additional storage within the VM.

    Create VM on Existing SSD:
        Go to Node > Create VM.
        Follow wizard and select local storage.
    Prepare Second SSD:
        Follow Task 1 steps to prepare second SSD.
    Pass Through Second SSD to VM:
        Shut down VM.
        Go to Node > Your VM > Hardware.
        Add second SSD as hard disk.
    Configure Second SSD within VM:
        Start VM and access console.
     
Partition and format second SSD:<br>
sudo fdisk /dev/sdb
sudo mkfs.ext4 /dev/sdb1
sudo mkdir /mnt/storage
sudo mount /dev/sdb1 /mnt/storage

Add to /etc/fstab for automatic mounting:<br>
echo '/dev/sdb1 /mnt/storage ext4 defaults 0 2' | sudo tee -a /etc/fstab

**Partitioning the second SSD** <br>
sudo fdisk /dev/sdb

**Formatting the new partition** <br>
sudo mkfs.ext4 /dev/sdb1

**Creating a mount point and mounting the partition** <br>
sudo mkdir /mnt/storage
sudo mount /dev/sdb1 /mnt/storage

**Adding to /etc/fstab for automatic mounting** <br>
echo '/dev/sdb1 /mnt/storage ext4 defaults 0 2' | sudo tee -a /etc/fstab
