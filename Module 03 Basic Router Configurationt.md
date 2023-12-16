## What is Router
Router is a networking device which is used to provide interaction between two different networks. Router Is also used for provide routes to the data beetween source to destination, establish internetwork communication

### Features Of Router
1. Routing: It Is a process to define path to travel data source to destination

2. Firewall: Handle , Filter And Control incoming and outgoing network traffic based on Pridefined security rules.

3. Wireless Capatibility: Support Dual bands 2.4 and 5.0 GHZ as per router specification.provide long access nd high speed internet.

4. VPN (Virtual Private Network): hide our public ip addresses and secure remote access also encrypte your data in network any unknown people does not see data packets.

5. Dual Stack :this features you have configure ipv4 and 6 address in same port.both ip address are ping

6. Quality of Service (QoS): Routers can Filter network traffic based on the type of data being transmitted. This ensures that critical applications and services receive adequate bandwidth and are not affected by lower-priority traffic.

### Advantages of Router
1. Easier Understand :  easy to install a new router and Every People understand router configrations.

2. Security: secure our network using Nat (Network Adreess Translator) create multiple privet ip address, Vpn

3. Remote Management:Allows users to manage and configure the router settings remotely. Using console,wireless or ethernet cable

4. Guest Network:Provides a separate network for guest devices with restricted access to the main network.

### Types Of Router:

1. Wireless :- It is Available in office, home or railway station, etc. It creates a wireless signal. Suppose you are in office, we can connect to the internet using WIFi because your laptop is within the range. We can provide security to routers by entering user id and password. When we try to connect to the router, it will ask for a password and User-Id.

### wireless Router 
![App Screenshot](https://www.netgear.com/zone3/cid/fit/1024x633/to/jpg/https/www.netgear.com/in/media/R6120_productcarousel_hero_image_tcm165-96410.png)

2. Wired Router : Wire is available to connect to the network. If we visit a bank or small college or office, we can observe that PC or Laptop is connected to the internet using Ethernet cable and that is the wired router. It has a separate Wi-Fi 

### wired Router 
![App Screenshot](https://us.123rf.com/450wm/chutima888/chutima8881708/chutima888170800109/83926103-hand-connecting-a-yellow-network-cable-on-a-network-port-of-a-router.jpg?ver=6)


3. Core Router :- Core router share IP packets at full speed on all of them. It will distribute data packets within the network. But core will not distribute data packets between networks.

### Core Router 
![App Screenshot](https://5.imimg.com/data5/OP/QI/MY-1151721/core-router-500x500.jpg)

5. Virtual Router :- virtual routers are pieces of software that allow computers and servers to operate like routers. They’ll share data packets just as physical routers do. They can offer more flexibility than physical devices since they can be scaled as the business grows.it is use core networks big buisnesses offices,they are also use as a backbone router

### Virtual Router 
![App Screenshot](https://www.sdxcentral.com/cdn-cgi/image/w=388,h=231,fit=scale-down,f=auto,q=85/https://www.sdxcentral.com/wp-content/uploads/2015/05/virtual-router-or-vrouter.jpg)



## Basic Cisco Router Configuration Step-By-Step Commands

![Cisco Router Practical](https://study-ccna.com/wp-content/uploads/2020/04/network_router_explanation.jpg)


### CLI Configuration Modes
The basic CLI modes that we will be referring below are as following:

```bash
Router> <– User EXEC Mode
Router# <– Privileged EXEC mode
Router(config)# <– Global Configuration Mode
Router(config-if)# <– Interface Configuration Mode
Router(config-line)# <– Line Configuration Mode
```

I assume that you already have some basic knowledge of CLI and how to
navigate between different configuration modes (user mode, privileged
exec mode etc), so let’s get started:

## Step-by-Step Configuration of Cisco Routers
Step 1 :- Configure Access Passwords

The first step is to secure your access to the router by configuring a global
secret password and also passwords for Telnet or Console as needed.
Enter into Global Configuration mode from the Privileged EXEC mode:

```bash
Router# configure terminal <– Privileged EXEC mode
Router(config)# <– Global Configuration Mode
```

In Global Configuration Mode you configure parameters that affect the
whole router device. Here we will configure the Enable Secret password
that you will be using from now own to enter into Privileged EXEC Mode
from User EXEC Mode.

```bash
Router(config)# enable password “somestrongpassword”
```

From now on, when you log in from user EXEC mode you will be asked for
a password.

It is suggested also to configure a password for the Telnet Lines (VTY
lines) which will secure your access when connecting via Telnet over the
network.

```bash
Router(config)# line console 0
Router(config-line)# password “strongTelnetPass”
Router(config-line)# login
```

Step2 :- Configure a Router Hostname
To differentiate your Router from other devices in the network, you should
configure a Hostname for your device.

```bash
Router(config)# hostname My-Router
My-Router(config)#
```

Step3 :- Configure IP addresses for Router Interfaces
This is an essential step in order for your router to be able to forward
packets in the network. The most basic parameter for a Router Interface is
the IP address. From Global Configuration Mode you need to enter into
Interface Configuration Mode:

```bash
My-Router(config)# interface GigabitEthernet 0/0
My-Router(config-if)# ip address 100.100.100.1 255.255.255.252
My-Router(config-if)# no shutdown
My-Router(config-if)# exit
My-Router(config)# interface GigabitEthernet 0/1
My-Router(config-if)# ip address 192.168.10.1 255.255.255.0
My-Router(config-if)# no shutdown
My-Router(config-if)# exit
```
Step4 :- Save your configuration
Save your current running configuration into NVRAM. This will overwrite the
startup configuration.

```bash
My-Router(config)# exit
My-Router# copy running-config startup-config
```

