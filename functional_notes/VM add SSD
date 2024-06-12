# VM Preparation

## Steps to Create VM on Existing SSD

1. **Create VM on Existing SSD:**
   - Go to `Node` > `Create VM`.
   - Follow wizard and select `local` storage.

2. **Prepare Second SSD:**
   - Follow steps to prepare second SSD.

3. **Pass Through Second SSD to VM:**
   - Shut down VM.
   - Go to `Node` > `Your VM` > `Hardware`.
   - Add second SSD as hard disk.

4. **Configure Second SSD within VM:**
   - Start VM and access console.
   - Partition and format second SSD:
     ```bash
     sudo fdisk /dev/sdb
     sudo mkfs.ext4 /dev/sdb1
     sudo mkdir /mnt/storage
     sudo mount /dev/sdb1 /mnt/storage
     ```
   - Add to `/etc/fstab` for automatic mounting:
     ```bash
     echo '/dev/sdb1 /mnt/storage ext4 defaults 0 2' | sudo tee -a /etc/fstab
     ```
