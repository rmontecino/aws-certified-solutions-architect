# ENI vs ENA vs EFA
1. **ENI: Elastic Network Interface**. Essencially a virtual network card.
2. **EN: Enhanced Networking**. Uses single root I/O virtualization (SR-IOV) to provide high-performance networking capabilities on supported instance types.
3. **EFA: Elastic Fabric Adapter**. A network device that you can attach to your Amazon EC2 instance to accelerate High Performance Computing (HPC) and Machine Learning applications.

## Elastic Network Interface
- A primary private IPv4 address from the IPv4 address range of your VPC.
- One or more secondary private IPv4 addresses from the IPv4 address range of your VPC.
- One Elastic IP address (IPv4) per private IPv4 address.
- One public IPv4 address.
- One or more IPv6 addresses.
- One or more security groups.
- A MAC Address.
- A source/destination check flag.
- A description

### Scenarios for Network Interfaces
- Create a management network.
- Use network and security appliances in your VPC.
- Create dual-holmed instances with workloads/roles on distinct subnets.
- Create a low-budget, high-availability solution.

## Enhanced Networking
- It uses **single root I/O vitualization (SR-IOV)** to provide high-performance networking capabilites on supported instance types. SR-IOV is a method of device virtualization that provides higher I/O performance and lower CPU utilization when compared to traditional virtualized network interfaces.
- Enhanced networking provides higher bandwidth, higher packet per second (PPS) performance, and consistently lower inter-instance latencies. There is no additional charge for using enhanced networking.
- Use where you want good network performance.

### Scenarios for Enhanced Networking
Depending on your instance type, enhanced networking can be enabled 
using:

-  Elastic Network Adapter (ENA), which supports network speeds of up to 100 Gbps for supported instance types.
-  or
-  Intel 82599 Virtual Function (VF) interface, which supports network speeds of up to 10 Gbps for supported instances types. This is typically used on older instances.

**In any scenario question, you probably want to choose ENA over VF if given the option.**

## Elastic Fabric Adapter

- An **Elastic Fabric Adapter (EFA)** is a network device that you can attach to your Amazon EC2 instance to accelerate High Performance Computing (HPC) and machine learning applications.
- EFA provides lower and more consistent latency and higher throughput than the TCP transport traditionally used in cloud-based HPC systems.
- EFA can use OS-bypass. OS-bypass enables HPC and machine learning applications to bypass the operating system kernel and to communicate directly with the EFA device. It makes it a lot faster with a lot lower latency. Not supported with Windows currently, only Linux.

## Exam Tips

**In the exam you will be given different scenarios and you will be asked to choose whether your should use an ENI, EN or ENA.**

- **ENI**
  - For basic networking. Perhaps you need a separate management network to your production network or a separate logging network and you need to do this at low cost. In this scenario use multiple ENIs for each network.
- **Enhanced Network**
  - For when you need speeds between 10Gbps and 100Gbps. Anywhere you need reliable, high throughput.
- **Elastic Fabric Adaptor**
  - For when you need to accelerate High Performance Computing (HPC) and machine learning applications or if you need to do an OS by-pass. If you see a scenario question mencioning HPC or ML and asking what network adaptor you want, choose EFA.