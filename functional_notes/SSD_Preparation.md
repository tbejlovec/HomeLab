# SSD Preparation

## Steps to Wipe and Prepare Second SSD

1. **Identify Second SSD:**
   - Navigate to `Node` > `Disks`.
   - Identify the second SSD (e.g., `/dev/sdb`).

2. **Wipe Second SSD:**
   - Click `Wipe` and confirm.

3. **Create New GPT Partition Table:**
   - Click `Initialize Disk with GPT`.

4. **Create ZFS Pool:**
   - Navigate to `Node` > `Disks` > `ZFS`.
   - Click `Create ZFS`.
   - Name pool (e.g., `mainPool`).
   - Select second SSD and choose RAID0.

5. **Configure Proxmox Storage:**
   - Navigate to `Datacenter` > `Storage`.
   - Click `Add` > `ZFS`.
   - Configure ID and select ZFS pool.

6. **Verify Storage Configuration:**
   - Check storage under `Node` > `Summary`.

### Key Code Listings

```bash
# Unmounting SSD
umount /dev/nvme0n1p1

# Checking for open files
lsof | grep /dev/nvme0n1p1

# Manually wiping SSD
dd if=/dev/zero of=/dev/nvme0n1 bs=1M status=progress
