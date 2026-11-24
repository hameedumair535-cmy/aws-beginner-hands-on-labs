Project 2: Attach and Mount an EBS Volume to an EC2 Instance

 Objective

The objective of this project was to create an Amazon EBS volume, attach it to an EC2 Linux instance, format and mount it, and configure it to mount automatically after a reboot.

 AWS Services Used

  Amazon EC2
  Amazon Elastic Block Store (EBS)

 Technologies Used

  Amazon Linux 2023
  Linux Terminal
  XFS Filesystem

  Implementation Steps

1. Created a 5 GiB General Purpose SSD (gp3) EBS volume in the same Availability Zone as the EC2 instance.
2. Attached the EBS volume to the EC2 instance named `My-First-Linux-Server`.
3. Used `lsblk` to identify the newly attached disk (`/dev/nvme1n1`).
4. Formatted the new volume with the XFS filesystem.
5. Created a mount directory at `/data`.
6. Mounted the EBS volume to `/data`.
7. Created a test file named `my-first-ebs-file.txt`.
8. Added the volume's UUID to `/etc/fstab` to configure automatic mounting.
9. Verified the configuration and rebooted the EC2 instance.
10. Confirmed that the volume mounted automatically and the test file remained available.

 Linux Commands Used

Identify the attached disk:

```bash
lsblk
```

Format the EBS volume:

```bash
sudo mkfs -t xfs /dev/nvme1n1
```

Create the mount directory and mount the volume:

```bash
sudo mkdir -p /data
sudo mount /dev/nvme1n1 /data
```

Create a test file:

```bash
sudo touch /data/my-first-ebs-file.txt
```

Check the mounted volume:

```bash
df -h
ls -l /data
```

Verify the filesystem configuration:

```bash
sudo findmnt --verify
sudo mount -a
```

 Persistent Mount Configuration

Added the following entry to `/etc/fstab` using the EBS volume's UUID:

```text
UUID=0038c8be-ee13-4d88-a22f-4611f82addee  /data  xfs  defaults,nofail  0  2
```

 Result

Successfully attached and mounted a 5 GiB EBS volume to an EC2 Linux instance. Configured automatic mounting through `/etc/fstab` and verified that the volume and test file were still available after rebooting the instance.

 What I Learned

 Creating and attaching EBS volumes.
  Understanding EC2 Availability Zones.
  Identifying disks using Linux commands.
  Formatting disks with the XFS filesystem.
  Mounting and checking storage volumes.
  Using UUIDs in `/etc/fstab`.
  Configuring persistent storage across reboots.

 Screenshots

Screenshots demonstrating the attached EBS volume, mounted filesystem, and successful reboot verification will be added here.

 Cleanup

Review and delete unused EBS volumes and other AWS resources when they are no longer needed to avoid unnecessary charges.
