# AWS Elastic Block Store (EBS)
Amazon Elastic Block Store (EBS) provides persistent block storage volumes for use with Amazon EC2 instances in the AWS Cloud. Each Amazon EBS volume is automatically replicated within its Availability Zone to protect you from component failure, offering high availability and durability.

## Types of EBS Storage
1. General Purpose (SSD)
2. Provisioned IOPS (SSD)
3. Throughput Optimised Hard Disk Drive
4. Cold Hard Disk Drive
5. Magnetic

## Compare EBS Types
Volume Type | General Purpose SDD | Provisioned IOPS SSD | Throughput Optimised HDD | Cold HDD | EBS Magnetic
------------ | ------------- | ------------- | ------------- | ------------- | -------------
Description | General purpose SSD volume that balances price and performance for a wide variety of transactional workloads | Highest-performance SSD volume designed for mission-critical applications | Low cost HDD volume designed for frequently accessed, throughput intensive workloads | Lowest cost HDD volume designed for less frequently accessed workloads | Previous generation HDD
Use cases | Most work loads | Databases | Big Data & Data Warehouses | File Servers | Workloads where data is infrequently accessed
API name | gp2 | io1 | st1 | sc1 | Standard
Volume size | 1 GiB - 16 TiB | 4 GiB - 16 TiB | 500 GiB - 16 TiB | 500 GiB - 16 TiB | GiB - 1 TiB
Max IOPS / Volume | 16,000 | 64,000 | 500 | 250 | 40-200

## Volumes & Snapshots Exam Tips

- Volumes exist on EBS. Think of EBS as a virtual hard disk.
- Snapshots exist on S3. Think of snapshots as a photograph of the disk.
- Snapshots are point in time copies of Volumes.
- Snapshots are incremental - this means that only the blocks that have changed since your last snapshot are moved to S3.
- If this is your first snapshot, it may take some time to create.
- To create a snapshot for Amazon EBS volumes that serve as root devices, you should stop the instance before taking the snapshot.
- However you can take a snap while the instance is running.
- You can create AMI's from Snapshots.
- You can change EBS volume sizes on the fly, including changing the size and storage type.
- To move an EC2 volume from one AZ to another, take a snapshot of it, create an AMI from the snapshot and then use the AMI to launch the EC2 instance in a new AZ.
- To move an EC2 volume from one region to another, take a snapshot of it, create an AMI from the snapshot and then copy the AMI from one region to the other. Then use the copied AMI to launch the new EC2 instance in the new region.

## Amazon Machine Image (AMI)
You can select  your AMI based on:
- Region.
- Operating system.
- Architecture (32-bit or 64-bit).
- Launch Permissions.
- Storage for the Root Device:
  - Instance Store (EPHEMERAL STORAGE).
  - EBS Backed Volumes.
- All AMIs are categorized as either backed by Amazon EBS or backed by instance store.
- **For EBS Volumes:** The root device for an instance launched from the AMI is an Amazon EBS volume created from an Amazon EBS snapshot.
- **For Instance Store Volumes:** The root device for an instance launched from the AMI is an instance store volume created from a template stored in Amazon S3.

## EBS vs Instance Store Exam Tips
- Instance Store Volumes are sometimes called Ephemeral Storage.
- Instance Store Volumes cannot be stopped. If the underlying host fails, you will lose your data.
- EBS backed instances can be stopped. Ypu will not lose the data on this instance if it is stopped.
- You can reboot both, you will not lose your data.
- By default, both ROOT volumes will be deleted on termination. However, with EBS volumes, you can tell AWS to keep the root device volume.