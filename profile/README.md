# Global IT/IOT SCADA Overview

## Solution Overview

The Global IT/IOT SCADA (“Gii”) is a complete and tightly integrated SCADA technology solution for hardware device data management and for services connected to this data. The benefits of the platform include providing a cohesive view of data, bridging organizational silos for more collaborative and effective management, providing access governance and security throughout an enterprise, providing ease of vendor management, and providing simple access to applications.

Gii allows users to process and store all information related to equipment and software modules' operation, location and settings. Allows users to activate the necessary event processing protocols (automatic changing of settings, sending notifications), depending on the incoming and predicted data. The management system has the following graphical interfaces: administration, visual control, inventory (including status tracking) of equipment and cable infrastructure. Supports REST and GRPC API. Provides sending notifications via (SMS, WhatsApp, Telegram, WeChat). Supports built-in media server (Gii Sstorage) for storing graphic, video and PDF files. Supports the Business Logic Manager (Gii Logics) to handle Python scripting. Supports MQTT (Gii MQTT Bridge), SNMP (Gii SNMP Bridge) and LoRaWAN (LoRaWAN Bridge) bridges for information exchange with external devices and third-party systems.

The platform is built using high performance and industry standard components on the backend side and provides a modern and powerful set of APIs available for its services to achieve high performance from one hand and extensive functionality from the other.

## Platform Architecture

![Image alt](https://github.com/Noshika-Trading-FZE/.github/blob/3d71c346dd746b0b10767d80bd46b5cce0701fa2/unnamed.jpg)

Gii is built using high performance and industry-standard components on the backend side and provides a modern and powerful set of APIs available for its services to achieve high performance from one hand and extensive functionality from the other:
- Gii Core and API- PostgreSQL based platform with REST/GRPC GraphQL application interface;
- Gii Logics - Python script processor;
- Gii Storage - File and media storage server;
- Gii Bridges - Set of MQTT, SNMP and LoraWan connectors;
- Gii Config - WEB based graphical inventory interface;
- Gii SCADA - WEB based main SCADA visualization interface;

## Platform Core

The Platform has in its Core leverages The World's Most Advanced Open Source Relational Database - PostgreSQL. It allows structured but very flexible data storage including high speed processing and very rich functionality exposed to other components of the system via APIs. Platform supports two types of APIs, namely gRPC and GraphQL,  which can be used for two typical use cases.  gRPC API is a high-performance Southbound API with functions set optimized to high speed processing of  device data flow and device control functions. GraphQL is a modern and powerful API technology with a rich set of functionality which makes it a perfect fit for UI and business logic implementation. GraphQL is used as a Northbound API.

## Data Feed: SNMP and Others

The key data-feed technology focus for the Gii is for SNMP-enabled units and systems. Gii is supplied with over one-hundred device drivers which allow the user full control and easy management of such devices deployed in the field. MQTT and LoRaWAN technology-bridge components are present in the basic package of the solution as well providing the product with a broad reach of hardware to control.

## Data Processing

Gii supports key data processing functionalities, namely, data storage, data organisation and data normalisation. The device management block includes a device driver layer over one-hundred device and unit drivers which deliver well-processed and structured data storage. Gii’s Objects and Schemas (similar to the Object Oriented Programming Class and Class Instance concepts), facilitate data processing through well-defined data structures of servers, routers and other devices.

## Remote Procedure Calls

In addition to normal uplink data processing, the device and unit drivers layer exposes on-demand functionality of hardware to the native as well as to the third-party platform applications. This includes, but limited to, device reconfiguration, triggering arbitrary functions like switch on and switch off, enable and disable and similar.

## Native Apps and Customization

On one hand, Gii allows easy and instant access to IT/IoT data coming from various sources and technologies and, on the other hand, it also provides the end-users with a full set of ready-to-use applications, namely, Gii Config and Gii SCADA. These applications are designed to be function and feature rich but are generic enough to host multiple most typical system and network management use-cases. The applications are built using an open framework approach and have all their business logic components exposed and available for modification to the user. This allows very easy and quick customization of the functionality if needed. At the same time, the list of built-in functions is very comprehensive and allows instant use of the solution out of the box.

## GraphQL API

Gii supports the modern GraphQL API, which significantly simplifies the access to the Platform functionality and allows subscription to live data within the same framework. GraphQL is an open-source data query and manipulation language for APIs, and a runtime for fulfilling queries with existing data. GraphQL was developed internally by Facebook in 2012 before being publicly released in 2015. For today GraphQL has proven its efficiency and is being used in many modern projects across the world.

## Drivers

Below there is a list of most commonly used drivers which are included in the generic device driver package of Gii. 

### Conntrack Driver

Connection tracking (“conntrack”) is a core feature of the Linux kernel’s networking stack that tracks the logical network connections or flows. This enables stateful packet inspection for iptables so you can identify all of the packets which make up each flow. Specifically, conntrack is a command line interface for the connection tracking system and is more flexible than /proc/net/ip_conntrack. With conntrack, you can show, delete and update existing state entries and listen to flow events.

The Conntrack Driver collects stats from Netfilter's conntrack-tools. Conntrack-tools provide a mechanism for tracking various network connections as they are processed by netfilter. At runtime, conntrack exposes many of those connection statistics within /proc/sys/net. Depending on your kernel version, these files can be found in either /proc/sys/net/ipv4/netfilter or /proc/sys/net/netfilter and will be prefixed with either ip_ or nf_. This Conntrack Driver reads the files specified in its configuration and publishes each one as a field, with the prefix normalized to ip_.

Since conntrack normally improves performance (reduced CPU and reduced packet latencies), you can use this driver in conjunction with the other drivers that collect network and system metrics to get a complete picture of your application stack. In order to simplify configuration in a heterogeneous environment, a superset of directory and filenames can be specified. Any locations that don't exist will be ignored.

### CPU Driver

When trying to answer questions about what is impacting the performance of your servers or determining what VM size to choose, one of the first set of bottlenecks you check are memorey, disk, and CPU. CPU metrics in particular are helpful to determine if the CPU is constantly being maxed out. Key metrics that can help uncover the issue behind the CPU being maxed will paint a picture of who is using the CPU (application, processes, or OS itself); which processes are demanding more cycles than the CPU can provide; whether the CPU is waiting for operations to complete; or whether it is doing no work at all.

Typically, when you are tracking metrics about CPU performance, you do this by collecting and reviewing memory and disk usage as well. The CPU driver gathers metrics on the system CPU that you can store in Pixel Central Station. You can also easily add memory, disk and a whole host of other metrics with the various drivers to help paint a complete picture of your environment’s performance. Using DV driver opens the door for lots of varied use cases.

Configuring the CPU Driver is simple as there are only a handful of configurations to set. They include whether to report per CPU stats or not, whether to report total system CPU stats or not, collect raw CPU time metrics, and then compute and report on the sum of all non-idle CPU states. You can point to your Pixel Central Station instances and start collecting and reporting on these metrics.
 
### Disk Driver

With the price of disk storage dropping every day, you may be wondering: Why bother monitor disk usage any more? Even though storage costs have gone down, you still need to monitor disk usage to ensure that your applications or processes won’t fail due to insufficient disk storage, which could lead to other failures. And this can be tricky if you're hosting someone else's files since you don’t know when and how much data they are likely to write to storage.

Actively monitoring your free disk space using the Disk Driver — an input driver — can prevent data loss, server downtime and failures by being alerted promptly when disk space availability is beyond specified critical thresholds.

Configuring the Disk Driver is simple, and you can start collecting disk storage metrics and storing it in Pixel Central Station in no time. You can specify thresholds and receive alerts when those thresholds are crossed and keep track of hard disk usage of your web servers, application servers, file servers and much more. Collect other relevant metric data like CPU and memory usage, and you will start to build a more comprehensive view of your infrastructure.

The Disk Driver gathers metrics about disk usage. Note that used_percent is calculated by doing used / (used + free), not used / total, which is how the unix df command does it.
 
### DNS Query Driver

DNS (Domain Name System) is a naming system for resources connected to the Internet — essentially the phonebook of the Internet. Monitoring your DNS records helps you ensure that the Domain Name System continues to route traffic properly to your websites, services, and electronic communications.

DNS monitoring is done to track DNS requests and servers for performance issues, and therefore keeping an eye on DNS performance at effective levels is a must for companies. Collecting these metrics with the DNS Query Driver will allow you to quickly store them in Pixel Central Station along with a number of other metrics that can help you gain a comprehensive view of your application, networks and more.

The DNS driver gathers DNS query times in milliseconds, similar to dig, a network administration command-line tool for querying the Domain Name System (DNS). Configuring the DNS Query Driver requires defining the network protocol, domain, port, and query timeout. You can start collecting DNS Query metrics to help you understand performance. You can set thresholds and send alerts to avoid any issues with DNS routing.

### Bcache Driver

Bcache is a cache in the Linux kernel's block layer, which is used for accessing fast disk drives. For example, flash-based solid state drives (SSDs) act as a cache for one or more slower hard disk drives as a read/write cache or read cache. It essentially creates hybrid volumes using older and newer technology, providing performance improvements in even the most demanding environments.

Bcache also brings with it a number of unique benefits, like the fact that it also minimizes write amplification by avoiding random writes and turning them into sequential writes instead. This essentially merges I/O operations together for the purposes of helping both the cache and the primary storage device. Not only does this improve the performance of write-sensitive primary storage like RAID 5 sets, but it also goes a long way towards extending the lifetime of flash-based SSDs that are used as caches — thus maximizing your return on investment.

SSDs provide significant improvement in performance over traditional rotating SATA and SAS drives while the costs of SSDs have also declined significantly; this makes it possible for more solutions to make the switch to SSDs. Previously, cost was a major hurdle that organizations needed to overcome when switching to SSDs, yet this is slowly but surely no longer becoming an issue as the cost of storage plunges dramatically. This, coupled with the fact that it's flash-based storage so there are no moving parts to break down on the inside of the device (thus reducing the possibility of data loss) means that more businesses are using SSDs (under heavier workloads) than ever before.

Bcache provides some useful metrics about how well your caches are performing, and these metrics can be ingested into an instance using the Bcache Driver. By default, the Bcache driver gathers metrics for all Bcache devices, but you can also restrict the metric collection to specified Bcache devices.

### Bond Driver

In general, network bonding is a term used to describe the combination of network interfaces on one host, all for the purposes of redundancy and/or increased throughput. This is especially important in terms of virtualized environments, where redundancy is a critical factor. Obviously, you want to do whatever it takes to protect that virtualized environment from loss of service due to a disaster at a single point of failure or physical link. Network bonding goes a long way towards accomplishing precisely that.

Network bonding is also helpful in terms of increasing not only the network throughput and bandwidth, but it's also ideal when looking for fault tolerance, when load balancing networks and more. This is not to be confused with the concept of teaming, which is essentially a new way to implement network bonding by way of a separately provided driver.

Bonding your networks increases network throughput for your users, so it is important to know the current state of these bond interfaces to ensure performance guarantees to your users.

By paying attention to what is happening during normal working conditions, you can also put yourself in a position to more quickly identify whenever anything starts to stray outside of those "default" boundaries. This insight can be a great way to spot a small problem and fix it right now, all before allowing it to become a much larger (and potentially more damaging) issue in the future.

The Bond Driver collects metrics so you know which interface is active, what the state of the bond interface is, and if there are any failures. Knowing this will help you to maintain these interfaces, and therefore keep your SLA promises to your customers. Furthermore, you can combine these metrics with metrics collected from other drivers like SNMP, NetFlow, and Cisco gRPC Network Management Interface (gNMI) to get a fully integrated view of your network health. By default, the Bond Driver collects metrics from all bond interfaces, but you can restrict the metrics to specified bond interfaces.

### Beanstalkd Driver

Beanstalkd is a simple, fast work queueing daemon. Its interface is generic, but was originally designed for reducing the latency of page views in high-volume web applications by running time-consuming tasks asynchronously. A queue is something that lets you store "jobs" in it and later retrieve them. And some of the key attributes of a queue are the ability to easily store and retrieve items, the ability to never lose a job, and the ability to access the queue from several different languages.

Beanstalkd measures metrics about the number of requests your application is receiving, as well as the status codes of the responses. Monitoring the total number of requests can help you pinpoint surges in traffic, while monitoring 5xx and 4xx responses is good error detection. The Beanstalkd driver gathers these metrics for ingest into Pixel Central Station where you can monitor your application and create alerts that trigger when thresholds are exceeded.

Setting up the Beanstalkd Driver requires that you enter the server information and optionally, the list of tubes to gather stats about. Once this is configured, the Beanstalkd driver will start sending metrics to your instance.

### Ethtool Driver

Ethtool is a standard utility program that can be used from a shell to control, or gather information from NICs using the ethtool userspace API. In the Information technology community, the term ethtool is usually used to refer to this utility program.

Gathering metrics on your Ethernet devices connected to your Linux system can help you troubleshoot Ethernet-card-related problems on a Linux system.

The Ethtool Driver pulls ethernet device stats. Metrics pulled are dependent on the network device and driver. Configuration of this input driver is simple: list the metrics you want or you want to ignore. Once you have set this configuration, then point the driver to your instance to start gathering metrics.

### Hddtemp Input Driver

When it comes to infrastructure monitoring, many people monitor processor temperature but fail to check hard drive temperature. Paying attention to the temperature of your hard drive is important because overheated hard drives may cause data loss, data corruption, computer crashes, or even hard disk failure. While other components like a malfunctioned processor or graphics card can be replaced, hard drive failure can be more costly and could lead to the loss of important files which may no longer be recoverable.

Hddtemp is a small utility (with daemon) that provides the hard-drive temperature via S.M.A.R.T. Note that this is only available for drives supporting S.M.A.R.T. (Self-Monitoring, Analysis, and Reporting Technology), a supplementary component for devices to monitor, store, and analyze the health of their operation. Metrics are collected (temperature, number of reallocated sectors, seek errors...) to measure the health, predict possible failures, and provide notifications on unsafe values.

The hddtemp utility comes standard with several PATA, SATA or SCSI hard drives to monitor and report hard drive temperature, so using this Hddtemp Driver is an easy way to capture hard drive temperature metrics as a part of your infrastructure monitoring stack. You can select which drive to collect these metrics against and compare it to other metrics about the hard drive’s performance from a number of other drivers to give you a holistic picture of the hard drive’s overall health.

The Hddtemp Input Driver reads data from hddtemp daemons. By default, the driver gathers temperature data from all disks detected by hddtemp. You can configure it to only collect temps from the selected disks. Because this driver reads data from the hddtemp daemon, hddtemp should be installed and its daemon running. Hddtemp requires root privileges, and the command hddtemp must be followed by at least one drive's location. You can list several drives separated by spaces.

### Other drivers

The list of the core drivers is extended with more than 100+ drivers for other hardware and software components which can be integrated into Gii SCADA and effectively monitored.
 
## Other Functions

In addition to its core functionality, Gii provides users with built-in group-based permissions management, generic-purpose notifications support (integrated with emails, SMS, WhatsApp, WeChat and Telegram), media files storage server and user management which can be shared across applications.

## Feature List

- Device Management: ensures the connected devices are working and interacting properly with the Platform.
- Database: scalable storage of device data.
- Unit Drivers Layer:  unit and device isolation and control.
- Data Representation Layer: unified hardware data representation.
- Schemas and Objects:  managing and ensuring integrity of data structures.
- Remote Procedure Calls: a mechanism to execute remote functions exposed by hardware units.
- Notifications: including SMS, emails, Whatsapp, WeChat, Telegram.
- Historical Data Storage: for later retrieval and processing.
- Users and user profiles: for user and access management
- Storage: general-purpose file server.
- Apps: Config, SCADA for visualisation and other management.
- Logics module: for event-worker handling.
- Modern GraphQL API External interfaces: integrate with 3rd-party systems and the rest of the wider IT-ecosystem via built-in application programming interfaces, software development kits, and gateways.
- Technology Bridges for supporting data feed over multiple communication technologies.


