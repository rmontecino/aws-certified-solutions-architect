# AWS EC2
Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides resizable compute capacity in the cloud. Amazon EC2 reduces the time required to obtain and boot new server instances to minutes, allowing you to quickly scale capacity, both up and down, as your computing requirements change.

## EC2 Pricing Models
1. On Demand: Allows you to pay a fixed rate by the hour (or by the second) with no commitment
2. Reserved: Provides you with a capacity reservation, and offer significant discount on the hourly charge for an instance. Contract terms are 1 year o 3 year terms.
3. Spot: Enables you to bid whatever price you want for instance capacity, providing for even greater savings if your applications have flexible start and end times.
4. Dedicated Hosts: Physical EC2 server dedicated for you use. Dedicated Hosts can help you reduce costs by allowing you to use your existing server-bound software licenses. 

## EC2 Instance Types
Family | Speciality | Use case
------------ | ------------- | -------------
F1 | Field Programmable Gate Array | Genomics research, financial analytics, real-time video processing, big data, etc.
I3 | High Speed Storage | NoSQL DBs, Data Warehousing, etc
G3 | Graphics Intensive | Video Encoding/3D Application Streaming
H1 | High Disk Throughput | MapReduce-based workloads, distributed file systems such as HDFS and MapR-FS
T3 | Lowest Cost, General Purpose | Web Servers/Small DBs
D2 | Dense Storage | Fileservers/Data Warehousing/Hadoop
R5 | Memory Optimized | Memory Intensive Apps/DBs
M5 | General Purpose | Application Servers
C5 | Compute Optimized | CPU Intensive Apps/DBs
P3 | Graphics/General Purpose GPU | Machine Learning, Bit Coin Minining, etc
X1 | Memory Optimized | SAP HANA/Apache Spark, etc
Z1D | High compute capacity and high memory footprint | Ideal for electronic design automation (EDA) and certain relational database workloads with high per-core licensing costs
A1 | Arm-based workloads | Scale-out workloads such as web servers
U-6tb1 | Bare Metal | Bare metal capabilities that eliminate. Virtualization overhead

## Exam Tips
- Termination Protection is turned off by default, you must turn it on.
- On an EBS-backed instance, the default action is for the root EBS volume to be deleted when the instance is terminated.
- EBS Root Volumes of your DEFAULT AMI’s CAN be encrypted. You can also use a third party tool (such as bit locker etc) to encrypt the root volume, or this can be done when creating AMI’s (lab to follow) in the AWS console or using the API.
- Additional volumes can be encrypted.