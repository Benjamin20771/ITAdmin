# ITAdmin
## Internship notes

### VMs

A VM (Virtual Machine) is a fully fledged "virtual computer" that your computer runs inside of itself. It feeds off the host computer resources in return acting as a fully usable computer (without any physical parts).

IT team members should be at the very least familiar with the operating systems that the Leahy Center commonly uses. Google is your friend here, and feel free to ask me or your coworkers for assistance.

The OS's you should know are


Windows 10, Windows 11 (Used by the majority of businesses today)
MacOS (Common among artists & creative majors, & it is always great be familiar with MacOS) It is much harder to virtualize MacOS on systems other than MacOS since it is a very closed source, but it is possible.

Linux (Very important! Linux is used for critical services for many organizations! It runs websites, keeps systems secure, and does many many things!)

### Subnetting 

There’s a very high chance that your home router was given to you by your ISP. That router was probably set up so that your home network uses a particular block of IP addresses, perhaps something like 192.168.1.X, where the X is anything from 0 to 255. Typically the router's IP is 192.168.1.1 (or 192.168.0.1).


In a sense, your internet at home is a "subnet". The practice of "subnetting" is splitting a larger network into smaller networks. We often use subnets to split a large network, one for hundreds or thousands of computers, into multiple subnets, each with its subnets beyond that. For a large car dealership, The Sales branch is a subnet, with small car sales and small truck sales under that.


--Another example--

Let's say Families 1 and 2 live on the same street. 192.168.1. Connor Street. They can see each other, and talk to each other since they are on the same street. Families 3 and 4 are on 192.168.2. Morgan Street, and thus cannot talk to those on Connor Street without driving (routing) to see them.

Since these are different streets (networks), they can't talk to each other without a method of travel, which is routing!!

### Leahy Center Infrastructure

![big-image](https://github.com/user-attachments/assets/291da51e-124f-4dfc-b564-155ee1bb396d)

Summary:

AD-01 & AD-02: Active Directory / Main servers. Your accounts are synced up to these, and password resets, account lockouts, so many things come from these.

DHCP-01 & DHCP-02: Assigns computers DHCP IP addresses based on a standard that we set. MAC Address filtering is also running on these.

Neptune: An SQL database server for many apps in our network.

Poseidon: A web server for multiple websites we host internally (such as the LC Homepage). These cannot be accessed from outside of the Leahy Center's network without a VPN.
Mediawiki: This will be where all of LC's documentation is hosted and also accessed. If you are unsure of something, it is most likely on Mediawiki. You have permission to add pages, but check to make sure if what you are about to add is already there or not.

TPM: This is our password manager, it has 2FA (two-factor authentication). If you need a device's credentials or need to remotely log into a VM, it's most likely on there

### Subnetting in the Leahy Center
The Leahy Center's infrastructure is split into various sub-networks, all of which have their important purposes.

Below is an abbreviated list of various subnets that IT members typically will work with. It is subject to change over time but this is current as of Fall 2024.

VLAN 101 - Internal / Critical Infrastructure

Critical Infrastructure, such as our VMware ESXi servers, are hosted on the 192.168.101.0/24 Subnet. These servers host tens to hundreds of virtual machines, like the ones you use in your lab assignments. One virtual machine for the Security team or IoT team may be on a different subnet than one for our IT team.



VLAN 102 - Workstations

Workstations in the Research Room and Managed Support Services Backroom are on the 192.168.102.0/24 subnet.

IoT = The massive pains on IT's side! Also known as the Internet of Things. Devices may not be completely organized according to their subnets.

VLAN 104 - IoT Infrastructure

This is typically reserved for IoT workstations but is subject to change with the recent addition of 106 below. It may also host IoT devices.

VLAN 106 - IoT-WKS

This has been recently added to the Leahy Center network and hosts both IoT devices and infrastructure.

VLAN 201 - MS-TestNet-1

This network is what your Intern training VMs should be hosted on. Formatted 192.168.201.0/24

