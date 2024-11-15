# networking-doc.md
  CHAPTER : 9
  #  <font color="YELLOW"> NETWORKING FUNDAMENTALS </font> 
         
## <font color="blue" align ="right"><center> CHAPTER LESSONS 
<br>
1- FUNDAMENTALS OF NETWORK PROTOCOLS --------> TCHANKOUMI USHER PHARELL BLONDI 



2- PERSISTENT NETWORK CONFIGURATION ----------> CELINE-CORALIE ENI BINA 
 


3- BASIC NETWORK TROUBLESHOOTING--------------> TEGHA ROMEO



4- CONFIGURE CLIENT DNS -----------------------> CELINE-CORALIE ENI BINA & TCHANKOUMI USHER PHARELL BLONDI 
   
  <br>


   ## <font color="grey" align="right"><center> LESSON 1 : FUNDAMENTALS OF PROTOCOLS  </font>
   <br>



  Hey everyone today we will discuss about Networking. We will see how it functions and key terms related to it.
 
 <br>
   At the end of this chapter the following objectives are to be achieve
  
  <br>

You should be able to                   
<br>

-    Know what is an IP address, a netmask address , a network address and a broadcast address and also how to calculate them
-    Know how to convert an ip address from binary to decimal and vice versa
-    Understand the OSI model
-    Know the differnt protocol use to transfer data
-    Differences between IPV4 and IPV6 address


<br>


### <font color="grey"><center> INTRODUCTION </font>
<br>
 We should know that for information to be send from one computer to another.  computer in the internet  essential requirements are needed.. among this we have 
  
  <br>
<font color="grey"> NETWORKING </font>
 
 <br> 

This refer to the designing,building and conceptuatising of software for infranstructures and networks . when we are talking of computer networking this refers to the interconnection of computers across the internet 

<br>


<br>
This is the unique identifier for every device connected to the internet  ..when a device is connected to the internet the DHCP(Dynamic Host Configure protocol) gives the device an IP adress.There exist two main types of ip  address that are PRIVATE and PUBLIC ADDRESS.<br>
Being the most used PUPLIC ip address are the one assigned to each computer on the internet but it is not very efficient because due to the fact that the population is increasing day after day the public ip have become too small to handle the ip of each other so a private IP have started be used 
<br>it is functioning just like a public IP by beeing assigning to any device in the internet but slightly differerent  in a way that when a public IP is giving to any device conncted to the internet ,it is given to any device conected in a LAN

  
  
  #### IPV4  AND IPV6 ADDRESS  

  
An ip address can be divided into two main types that is the IPV4 address and the IPV6 adresss..Firstly in the begining of the days the type of IP adress used was the IPV4 address but becuse of many DHCP configuration and  alot of population an IPV6 address which can take a very large population.

 #### CONVERSION FROM DECIMAL FORMAT TO BINARY 

For an address to be converted to binary each section on the ip address is reduced to binary that is ....as an example of an ip we can have 192.168.0.123  , so here the 192 is first converted to decimal  by deviding by 2 until its lowest form and recording the remainders an then at the end record the remainders in ascending orders .. so you will do these for all the sections of the ip address and then record their value in binary ..

#### CONVERSION FROM BINARY TO DECIMAL 
  If you want to convert to decimal take each binary section and place it arrays of bits ex..lets us consider the following the following binary IPV4 address 11100011.1100111.10100000.000000000 

- firstly this will be place in rows of bits that is
                      2^7   2^6  2^5   2^4  2^3    2^2     2^1  2^0
- Now you have to place the fist section of the IP address
  
        2^7     2^6     2^5    2^4      2^3     2^2    2     2^0
  
        1      1        0     0      0        0        0    0
  
- From here you will now take the digits and multiply them by the corresponding bits on which they are placed  and then add them that is
       
       1*2^7 + 1*2^6 + 0*2^5 + 0*2^4 + 0*2^3 +  0*2^2 + 0*2 + 0*2^0 = 192
- The same steps will be done on the rest of the binary digits until finnaly you will obtain a complete ip address in decimal


  Other exmaples of address are
1- NETMASK ADDRESS: This address is used to determine how many bits of IP address is the network address it is having a default value of 255.255.255.0.In the network address 02 bits are automatically assigned  that is the "0" for the network address and the 255 at the end for the broadscast adress. Each section on the netmask address is made up of 8 bits.
  
2- NETWORK ADDRESS : This is a special address that is used to define a paricular network.This address is obtained by  doing a bitwise AND (&) between the IP and the NETMASK ADDRESS  that is

   Let us take an ip address that is 192.168.0.128 and a Netmask address that is 225.255.255.0. So these addresses will be converted to   binary and  then bitwise AND (&) that is  255 converted to binary will give 11111111  and 192 will give 11000000
  
   so this can reprensented as

       1 1 1 1 1 1 1 1  
       1 1 0 0 0 0 0 0
Then a bitwise AND($) between the 02 will give me a result of  11000000 and that when converted to binary will give a reult of 192, the same process with be done and the second section of both address will be take..that is 

 168 on the ip address when converted to decimal will give 10101000 and the 255 on the netmask will still give 11111111..then the sane process will be done  

       1 1 1 1 1 1 1 1 
       1 0 1 0 1 0 0 0
 So when this two are bitwise AND (&) the result obtained is 10101000 that will still give me 168 when converted to decimalwhen we take the third section we have 255 given 11111111 and 0 given 00000000 this will give 00000000 when bitwise AND (&) so we will return a 0 on the third section and for the last section we will have 0000000 from the netmask address and  128 on the Ip address last coloumn will give 10000000 and this will still give 0 when bitwise
  Then at the end we will have 192.168.0.0 which will represent our Network address.We can realise that the first 03 section of the Ip address is given us our network address.This is the reason why an IP address is divided into 02 main part the network address that are the first 03 coloumn and the host address that is on the last coloumn.

3- BROADCAST ADDRESS : This is a special address that is used to send packets to other devices on the same network .This can be obtain by applying a not on the netmask adress and doing an OR operation on the IP address 

that is having an IP address 192.168.0.128 converted to binary give 11000000.10101000.00000000.10000000 and then negating the Netmask will give instead of 11111111.11111111.11111111.00000000 will be converted to 00000000.00000000.00000000.11111111 and then an OR operation will be aply with the IP address and the result obtained will be our Broadcast address.
  
   More information about our addresses can be seen through the ifconfig command 
   
  CIDR : name fully as CLASS INTER DOMAIN ROUTINE :This allows networks routers to route data packets to the respective device based on the indicated subnet
  

   Know we will see how data is being transfer through the network and we will use one of the great model that has been used till up date called the OSI MODEL.

#### OSI MODEL(OPEN SYSTEM INTERCONNECTION)

This model ia a conception model of how internet works and is divided into seven layers. We can have  the following diagram for the different level of OSI MODEL  
 
   ![image](https://github.com/user-attachments/assets/e55cfd01-ccb8-4a8c-8c8d-92441a21c0aa) 

WE should note that  the OSI model is functioning fron sender to receiver and from receiver to sender .SO the explanation under the 7 layers are as follow 

- ##### APPLICATION LAYER

When data is  send from sender to reciever this is the first layer through which information pass..This layer function in sending data to the reiver and the reciever on its side will send back the end user .
   it layer provide the protocols that allow  software /apps to transmit data exmaples are 
HTTPS and HTTP,
FTP ,
POP & SMTP,
DNS,
TELNET,
DHCP,
-SMTP

- ##### PRESENTATION LAYER

This layer ensures that data is prepared for the application layer (receiving side) or for the network layer (sending side).It is responsible of some tasks like 
- data translation
- Encryption & decryption of data
- Compression of data
- Other data presentation items

- ##### SESSION LAYER

This layer creates and maintains the sessions that 02 systems neede inorder to speek to each other ... This layer take in charge the mode of data transmition being  duplex,half duplex and full duplex . This layer defines 
- when sessions are created and opened
- How long sessions remain open to sucessfully exchange data
- when to close sessions

- ##### TRANSPORT LAYER

  Also called as the heart of the OSI layer , this layer use the TCP(Transmition control protocol) and the UDP(User datagram protocol ) ,to manage network traffic between systems and ensure correct data transfers they function also in the followiing ways
  - On the sending side, it takes data from the session layer and breaks it into segments for the network layer.
  - On the receiving side, it reassembles the segments from the network layer and passes them on to the session layer.

This layer also handles flow control and error control, regulates transmission speed and requests retransmissions if needed. As we said this layer deals with this 02 maiin protocol that we will discuss below 
Vide
 - ###### Transmition control protocol

The transmission control protocol (TCP) is defined as a connection-oriented communication protocol that allows computing devices and applications to send data via a network and verify its delivery, forming one of the crucial pillars of the global internet.

 ![image](https://github.com/user-attachments/assets/5826d112-2d60-4c50-83cc-ae34a7083108) 
 
   example of  transmission control protocol in real life scenarios are 
  - email
  - text messaging
  - file transfers

- ###### USER DATAGRAM PROTOCOL
User datagram protocol (UDP) is a message-oriented communication protocol that allows computing devices and applications to send data via a network without verifying its delivery, which is best suited to real-time communication and broadcast systems.

![image](https://github.com/user-attachments/assets/5ec01dc3-b2bf-454d-be10-59fdec715531)

 examples of User datagram control protocol in real life are 
 - DNS lookup
 - Online games
 - Videos streaming

Both of these uses  PORT which is used to reach the corresponding device on a particular network

- ##### NETWORK LAYER

This layer decides which path the data will take so  as to reach the receiver in case it is coming from .its responsible for breaking up transport layer segmenst into smaller network packets foer tranmission and for reassembling those packets on the receining systems 

- ##### DATA LINK LAYER

This layer defines the format of data on the network .It and uses Media acess control for flow control and multiplexing between the 02 systems 

- ##### PHYSICAL LAYER

   This layer describes the  physical connection between devices in a network, here this layer deal with the material through which data is being received  or transfer . examples of device in the  physical connection layer is coax/fiber,wireless,hubs,repeaters
   SO 


this processses generalise how data is being transmitted on the network 


 # Persistent Network Configuration
# Introduction:
In any TCP/IP network, every node must configure its network adapter to match the network requirements, otherwise they will not be able to communicate with each other. Therefore, the system administrator must provide the basic configurations so the operating sytem will be able to set up the appriopriate network interface and these network configurations are stored under the /etc directory to bring up network connectivity during boot time. 

## The Network Interface 
A network interface is a point of connection between a private and a public network. It enables data to be sent and received between the computer and other network-connected devices such as routers or switches.
### Network Interface Cards(NICs)
A Network Interface Card (NIC) is a computer hardware component that enables devices, such as computers or servers, to connect to a computer network.
#### Rules used by the OS to name and number network interfaces 
From higher  to lower priority, the following rules are used by the OS to name and number the network interfaces:
1. Name the interface after the interface after the index provided by the BIOS or by the firmware of embedded devices, e.g. eno1.
2. Name the interface after the PCI express slot index, as given by the BIOS or firmware, e.g. ens1.
3. Name the interface after its address at the corresponding bus, e.g. enp3s5.
4. Name the interface after the interface's MAC address, e.g. enx78e7d1ea46da.
5. Name the interface using the legacy convention, e.g. eth0.

In older times, Linux distributions named network interfaces as eth0, eth1, eth2 and so on. Where 0, 1 and 2 were decided by the kernel. But recently, the network interfaces in Linux machines are named wlan0, eno1, ens1, enp3s2 as such. The probem with the old naming was that it was based on which the kernel sees first when booting i.e when the kernel is booting up the first card it sees is the eth0, second eth1, third eth2 and so on.This strategy was not good enough because an update could change the whole thing and that's because if you install a new distro they may change. So with the recent ones like the wlan0 for wireless interface cards and enp3s2 which is the most common one can exactly show you there is a network card, where it is located on your computer bus and which slot. Meaning if this NIC is physically inserted into the computer, in all Linux OS it will have the same name which was a much better strategy. Also, these names can be checked using different commands. In older times, we used the ```ifconfig``` commnand which shows all the network interfaces which are up and running. But nowadays, we use the ```ip link show``` command which shows all the links(NIC). Also, note that the ```ifconfig -a``` shows all the devices and not only the devices which are up and running.
 
 ### Network configuration 
  Refers to the process of organizing and maintaining information about all components in a network, used for updating, reparing or expanding the network.
  ### Configuring Network Interface Cards
  There are different commands which can be used to configure a network interface card. It can be done permanently with configuuration files and temporarirly with some commands like ```ifconfig``` which was an older command used in configuring interfaces. For example, if you want to configure a particular NIC you can input the ```ifconfig```command, specify the device and its ip address e.g
  ```sudo ifconfig enp0s25 192.168.42.42```
  You need the sudo access because you are changing a very critical configuration on a network. These interfaces are configured so that more infomation will be provided to make them usable and provide them ip addresses. You can also include the netmask, for example you will input the ```ifconfig``` command, specify the device and the netmask and the configuration will be set. Or better still you can do this in one command e.g,
  ```ifconfig eth0 192.168.0.1 netmask 255.255.2.0``` and ofcourse with sudo access. All these processes I've explained above are not permanent changes we were just issuing a command to configuring an ip address on a device. But if you want to make it permanent you can configure them in configuration files.
  With debian based distributions, we have the /etc/network/interfaces but with redhat based distributions we have the /etc/sysconfig/network-scripts/. Also, with redhat machines you can simply input the command ```ifup eth0``` and the ```ifup``` command will lookup this file on redhat and configure it. We can also use the ```ifdown eth0``` command and it will bring the network interface down.
  Nowadays, most of the new distros use the ```ip``` command.  With this ```ip``` command, you can configure networks and their routing.
  ###### Note: The ability of a network interface to have multiple ip addresses stems from a combination of virtual interfaces, router functionality and ipv6 capabilities.  

### Network Manager and ```nmcli```
This service can "watch" the status of a network and various configurations and configure the network cards accordingly. The ```nmcli```(networkmanager commnad line interface) is a program which controls the network manager and communicates with the network manager. By default, the networkmanager daemon controls the networks which are not mentioned in the /etc/network/interfaces. This service runs in the background and controls the NICs which are not configured there. Various frontend GUI(Graphical User Interface) ot TUI(Textual User Interface) or CLI(Command Line Interface) programs exists to control or configure the networkmanager daemon. To connect to a wifi network you can use the command;
```nmcli device wifi connect Hypnotoad```
The command to check the hypnotoad is ```nmcli device wifi list``` so that you can verify the name of the network you want to connect to.
And to check the current status of the network, you can use the command ``` nmcli general``` or if you want to check the devices or list of wifi connections use the command ```nmcli device```.

### Configuration with the Hostname, Hosts and DNS
To begin with, a hostname is a label assigned to a device that identifies it on a network. The machine's name is found in the /etc/hostname although it can be changed temporarily or permanently. To change the hostname of your computer you can use the command ```hostnamectl set-hostname new_name```. Also, you can set the prettyname using the command ```hostnamectl set-hostname --pretty "name"```. Like I said earlier, it is equally possible to change the system's hostname to a temporal name and you can do this using the command ```sudo hostname newname```. Also note that the /etc/hosts file contains IP addresses and their hostnames.
The DNS(Domain Name System) is a service which translates human readable  domain names to their corresponding ip addresses. Normally, you have to configure your computer to use the DNS so it will know which IP address to contact if you want to reach  linux1st.com. The configuration can be found in the /etc/resolve.conf. If you want to convert a certain domain name into its corresponding ip address you can ping the domain name and then you will have the ip address. For example, this command ```ping google.com``` will convert the domain name google.com to its ip address. 
We also have the nsswitch(nameserviceswitch) which is stored in the /etc/nssswitch.conf and its used to configure which services are to be used to determine information such as hostnams, passwords files and group files.

### Systemd-Networkd
Systemd-networkd is a network daemon provided by systemd that manages network interfaces and configurations. Systemd has daemons that can manage not only network interfaces through the systemd-networkd daemon, but it can also use systemd-resolved to manage local name resolution.
The configuration files used by systemd-networkd to set up netwrok interfaces can be found in any of the following three directories;
###### /etc/systemd/network: This is the local administratiom network directory.
###### /run/systemd/network: This is the volatile runtime network directory.
###### /lib/systemd/network: This is the system network directory.
Note that they have been listed in order of priority.
These files are processed in a lexicographic order so it is recommended to start their names with numbers to make the ordering easier to read and set. So the files in /etc have the highest priority followed by /run then /lib. This means if configuration files in different directories have the same names then systemd-networkd will ignore the files with lesser priority.
The purpose of each configuration file depends on its suffix. That is,
netdev: They are used by systemd-networkd to create virtual network devces such as bridge or tun devices.
.link: They set low-level configurations for the corresponding network interface.
.network: This is the most important suffix. The files using this suffix can be used to set up network addresses and routes.
The network interface to which the configuration files refer to is identified in the [Match] section inside the file. There is also a "Name=" entry that can be used to reference a specific interface and there is  a "MACAddress=" entry.
Here are two files that could be used to define interfaces using a statically-provided ip address and gateway and one that uses DHCP(Dynamic Host Configuration Protocol)
[Match]
MACAddress= 00:16:3e:8d:2b:5b
[Network]
Address= 192.168.0.100/24
Gateway= 192.168.0.1

[Match]
MACAddress= 00:16:3e:8d:2b:5b
[Network]
DHCP= yes
The "DHCP=" entry can aslo have the values ipv4 and ipv6.
###### Note: It is possible to use systemd for wireless network interface configuration with a password.

### Name Resolution Process 
Programs that resolve names to numbers almost always use functions provided by the standard C library on Linux systems. The first things these functions do is read the file /etc/nsswitch.conf for instructions on how to resolve that type of name. Once the process reads the /etc/nsswitch.conf, it looks up the name in the manner specified. Since /etc/nsswitch.conf supports plugins, what comes next could be anything. After the function is done looking up the name or number, it returns the result to the calling process domain name system (DNS).

### Other Matters 
To host another user in your computer, you  can use the commnand 
```ssh hostname@ipaddress```
With this command you will automatically host the user in your own computer and be able to access their directories.
To calculate the network address, convert the ip address and netmask to binary and do an AND Gate between the them.
To calculate the broadcast address, negate the netmask after it has been converted to binary and convert the ip address to binary then do an OR gate between the both of them.
To calculate the CIDR(Classless Inter-Domain Routing) value, convert the netmask address to binary then to decimal.
CIDR is a method of allocating IP addresses for efficient routing on the Internet.
A Broadcast ID is a special IP address used to transmit messages and data packets to all devices on a Local Area Network (LAN).
A network address is a unique identifier assigned to a node or host to distinguish it from other nodes or hosts on the same network.

  #   BASIC NETWORK TROUBLESHOOTING
> Key areas of understanding
- Manually configure  network and changiing their configuration
- Manually configure routing and changing their configuration
- Debug problems associoted with network

> some basic network troubleshooting  commands and their function
- ip, hostname, ss, ping, ping6, traceroute, traceroute6, tracepath, tracepath6, netcat,route
##         INTROUDUCTION
> what is a network troubleshouting : this refers to that aspect in computer science wheer we are dianose a network to ensure ***connectivitvity***, ***performance*** and ***functionality***
<br>

all know, linux is a flexible and has a very powerful network interface it plays a very great role in network troubleshooting and configuration within ipv4 and ipv6 networks
<br/>
- The main toool network troubleshooting are called * packet sniffers * such as the tcpdump and are useful in troubleshooting.

> As simple denition we could think of packet sniffers as tools that allows you to monitor and record packets that
  that enter or leave the neetwork interface
- Hex viewers can be used to view packets in detail than packet sniffers 

##        Netmask & routing review
- ipv4 and ipv6 are known as ***routableprotocols*** . This means that they play a very great role in managing network trafick .
- It also importantant to note others like Ethernet are not routableprotocols protocols because the play little or no role in handling network traffic .
- Both ipv4 and ipv6 have two sections i.e 
(1) network section and 
(2) host section 
As earlier discussed, the number of bit that make up each network section is called the ***netmask*** or ***subnetmask*** or ***prefix length***
- The neetwork portion looks up which part to be send out on its routable in both ipv4 and ipv4
- Its important to equally note that in asituation where the ipv4and ipv6 receives packages that are not their the try to match the device for which this was destine for
- if destination is found the package is send otherwise a ***default route*** is created
-  lastly if no destination is found nor a default route the package is automatically discarded .
***This play and essential role in troubleshooting ipv4 and ipv6***
 
##        configuring network interfaces
- The 2 basic ways of configuring interfaces are: ****ip**** and ****ifconfig****
- if config is the tools ***legacy toool*** and is the old configuration tool though not longer in use, though not really in use today like the ip 
- Before configuring a network interface its important to first know which interfaces are available. to do we use either of the following commands: 
(1) **ifconfig -a** 
(2) **ip link show**
- now assuming the /sys/class/net file system is mounted i.e
> ls /sys/class/net 
this will list all network that are monted on your machine

now to configure a network with ifconfig 
> ifconfig enp1so 192.168.50.50/24

- It good to know tha inlinux the version of ifconfig is flexible
> ifconfig eth2 192.168.50.50 netmask 255.255.255.0
 ifconfig eth2 192.168.50.50 netmask 0xfffffff00
 ifconfig enp0s8 add 2001:db8::10/64

- it should be noted that the case of ipv6 ***add*** was use
- to configure network interfaces using ip:
> ip addr add 192.168.5.5/24 dev enp0s8
ip addr add 2001:db8 ::10/ dev en0ps8

- we see that this works for both ipv4 and ipv6


## configuring low  level interfaces
- The command use here is the ***ip link*** and is use in confiring low level interfaces like MTU, VLAN etc
- ip perform common task such as to enable or disable interfaces
> ip link set dev enp0s8 down
  ip link show dev enp0s8
  ifconfig up enp0s8
  ip show dev enp0s8

# Routing Table
- tools like ***route***, ***netsta -r***, ***ip route*** are use in viewing the routing table
- to view the routing the routing table for ipv6 use:
  (1) ***route -6***
  (2) ***netstat -r6***
  (3) ***ip route -6***
- it should be noted that the ouput of netstat -r6 and route -6

***some paremeters and their significance when using rout commands***
(1)U-flag : This flag indicates the route is up
(2) ! : means reject route i.e route wont be used
(3)n-flag : Thsi flag means the rroute hasn't been cache i.e th kernel keeps track of the the route separately from other route
(4)G-flag : This flag indicates a gateway to the neetwork
(5) Metric or Met: This is not store within the kernel and refers to adminisrtative distance to the target . Think of the ***adminisrative distance*** as the distance used by routing protocols to det emine dynamic route.
(6)ref-column : refernce accout or simply number of use in use and not foud also used by the kernel
(7)use-colunm : this shows the number of lookups for a route
(8)MMS: Found in nestat -r and indicates the max segment size in TCP connection over the route
(9)window -colunm : shows the defoult TCP window size
(10)irrt: shows the shows the round trip packets on this route

## managing network interfaces
- route can be manage usig the ***route*** or ***ip route***
- To add an unterface using route
> ping6 -c 2 2001:db8:1::20
 route -6 add 2001:db8:1::/64 gw 2001:db8::3
 ping6 -c 2 2001:db8:1::20
- to remove interface using routableprotocols

> route -6 del 2001:db8:1::/64 gw 2001:db8::3
ping6 -c 2 2001:db8:1::20 

**lesson 3** : 
As earlier mention linux has alot of tools for troubleshooting a neetwork with. in this section we are expected to have a brief knowlege of the OSI layer.

## Testing Network Connection

**ping** and ***ping 6*** are use both use to send ICMP echo request to ipv4 and ipv6 respectively

- An ICMP echo request send a smal amount of data to the destination address. if not reachable it will send an echo reply message to the seder with the same data that was send  to it.
> ping -c 3 192.168.50.2
  ping6 -c 3 2001:db8::10
  
  - It should be noted that the -c option specify the number of packets to send others ping will continue sending the packet unless stop ctrl + c on your keyboard
  >It should be noted that you can't ping a hos does meam you can't connect

***traceroute*** and ***traceroute6*** can both be use to monitor the route a packet takes to reach its destination
how is done?  They do so by sending multiple packets to the destination incrementing the Time-To-live of the header with each subsequent packet .
Each router will then respond with an TTL exceeded ICMP message

>  traceroute 192.168.1.20
   traceroute6 2001:db8::11
   
   by default traceroute send package to port number 33438 incrementing it each time a packet is send .
   
   > using traceroute with the -I option enables you to use echo ICMP request insead of of UDP. this very effective because the destination host is more likely to respond to ICMP than UDP 

   traceroute -I learning.lpi.org
   In some scenarios an organization block their ICMP echo request and replies. To get aroud this you can use a known TCP port that guarantee you with the fact that the destination host will respond .
   
   - to use the TCP use the -T option along -p option to specify the port . 
   > traceroute -m 60 -T -p 80
learning.lpi.org

## Finding MTUs with tracepath
- the tracepath is semilar to the trraceroute but the difference is that it is use to ***Maximum Transmission Units***,MTU along the path
- The MTU is either configure interface on anetwork or a hardware limitation of the largest protocol data unit that it can transmit
- so the key difference is that tracepath uses very large UDP datagram unlike traceroute.

> tracepath 192.168.1.20
tracepath 2001:db8::11
tracepath6 2001:db8::11

The advantage of tracepath over  traceroute is on the last it ouput the smallest on the entire link. this very useful in troubleshouting connections that con't handle fragments. 

## creationg arbritrary connections
The nc program, known as netcat, can send or receive arbitrary data over a TCP or UDP network
connection. The following examples should make its functionality clear.
> nc -l 1234

- The output of LPI Example appears after the example below, which is setting up a netcat sender
to send packets to net2.example.net on port 1234. The -l option is used to specify that you wish
for nc to receive data instead of send it. 

>  nc net2.example.net 1234
Press Ctrl + C on either system to stop the connection.

- Netcat works with both IPv4 and IPv6 addresses. It works with both TCP and UDP. It can even be
used to setup a crude remote shell.
- Note that not every installation of nc supports the -e

> hostname
net2
 nc -u -e /bin/bash -l 1234

 - The -u option is for UDP. -e instructs netcat to send everything it receives to standard input of the
executable following it. In this example, /bin/bash.

## viewing status of current connections and listeners

The netstat and ss programs can be used to view the status of your current listeners and
connections. As with ifconfig, netstat is a legacy tool
-The examples below show the output of a commonly used set of options for both programs:
>  netstat -tulnp
ss -tulnp


 ## LESSON 4 : CONFIGURE CLIENT ADDRESS DNS
  
   At the end of this lesson  we should be able to 
      
- EXplain what is meant by NAME RESOLUTION 
 
- know what is all about  DNS classes and their signification 

- know how to resolve namesnames usind DNS 

- know what all about is the comand  the /etc/nsnwitch.conf ,/etc/resolv.conf, /etc/hosts 
- kmow about SYSTEMD-RESOLVE

- know some reolution tool and know how  each of them are applied 


### INTRODUCTION 

 - #### NAME RESOLUTION 
This is the  process of converting names into IP address  so that  computers  can communnincate with each other ..It can also be define as the process of associating names and IP address
 
 Program resolving names uses functions proided by  the standard libary that in linux is called the GNU project glibc .This function will read the file /etc/nsswith.conf which will give information  about how to resolve to resolve this type of name .As this /etc/nswitch.conf supports pluggin then anything can folow. 

- #### WHAT IS ALL ABOUT /ETC/NSSWITCH. CONF??
This  is a file that contain instruction on how to resolve a particular type of name . This can be display  using the command  

                     cat /etc/nsnwitch.conf 

 In this file the first coloumn on the left is the name database while on the right coloumn we have  sources .If the user is looking for a particuler host name  it will move on the left and look on the line starting with host then it will resolve the name using DNS 
   
   If  you see [!unavail=return]  this means if DNS  is unavailable then dont move to the next source but if  DNS is available move to the next source 

   If you have  on the source coloumn [result=action] this means that when a you look up at the name on the left coloumn if what is found on the right coloumn can resolve it then perform an action , but if a ! is place infront of result then this means that if what is found on the next coloumn cannot resolve the name then still perdform action .
   
   If a process is trying to resolve a port number to a service ,it will find for athe service line in the first coloumn.The first source listed is the NIS (Network INformation Service) 

   If on the source coloumn there is [ NOT FOUND=RETURN ]  this means that if the service is not found stop looking up and return . SO these are the information that ca  be found under the /etc/nsswitch.conf


- #### WHAT IS A DNS AND WHAT ARE IT'S DIFFERENT CLASSES??
 DNS in full can define as DOMAIN NAME SYSTEM, It turns domain names into IP address which browsers use to loads the Internet.
 
 A DNS CLASS is a static class that retrieves information about  a specific host from The Internet  Domain Name System (DNS). There exist 03 classes of DNS that are IN(INTERNET),CH(CHAOSNET)and HS (HESOID).
 
- ##### Internet 
This class is for internet addreses using the TCP/IP stack , this indicate that a particular record is of the internet class 

- ##### CHAOSNET 
This class is used to simulate wrong DNS responses 

- ##### HESOID
It uses DNS functionality to provide access to databases of information that change infrequently.some examples of database that cahnge inrequently are /etc/passwd and /etc/groups.

 
- #### WHAT IS ALL ABOUT /ETC/RESOLV.CONF ??
It is used to configure host resolution via DNS.IT defines how the system uses DNS to resolv host names $ IP address .

Information about this file can be dispaly using the command  
      
                  cat /etc/resolv.conf
Here you cand find the IPv4 and IPV6 address of a DNS server 

- #### WHAT IS ALL ABOUT /ETC/HOSTS FILE ??
This File is used to resolve  names to IP address and vice versa.On the left coloumn there are IP address and on the right are names associated with those Address 
..Information about the file can be display using the command 
                        
                  cat /etc/hosts



- #### SYSTEMD-RESOLVED 
It provides a service  known as systemd-resolved that provide network name resolution to local to local applications.
It provide LLMNR (link-local MUlticast Name Resolution)resolver and MulticastDNS resolver and responder
 
- #### NAMING REOLUTION TOOL
 These are tools use during name reolution .There exist many naming resolution tool but we are to focus only on three on these lesson 

1- GETEND
This tool is use to display entries from a name service database ex..
                         
                         getent hosts 
This will list all the host but you can specify the host you want depending on the  result of this command 

 You can use the option -s to force getent to use a specific data source ex of source can be files
  
2-HOSTS

It is asimple program for looking up DNS entries ,If host is given a name it will retu
rn an AAAA and SMX record where AAAA will provide the IPV6 address of the name and MX will provide the mail of the name .Both SMX and AAAA are records type 

 You can use the -t option to specify the record type that is 

               host -t [record type] [domain]
 

3-DIG
    
It have for full meaning Domain INformation Groper.It is a flexible tool for interogating DNS servers. It performs DNS lookup and display the answer that are returned from the queried name servers .It is more suited for troubleshooting 
 
So you can place dig with the database name  that is

                    dig [ database name ]

 Just like host you can specify a given record type using the same  command syntax..Dig have also other  option like
 
 - +SHORT: This option can be used to suppress the given informstion and take only the needed one 

 - NO : This is use when you want to display everthing exept a paticular one .this can be expressed as 
                   
                dig +nocookie -t MX lpi.org

  SO we are at the end of the cahpter NETWORKING I hope everyone understood what networking is all about .. see you next 








   
   

  
   
    



    
        
 























































   
