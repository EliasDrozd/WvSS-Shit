# Setup Guide - Domain Controller

## ISO-File

For the Assessment we have two available ISO-Files:

```
Windows Server 2025 v2.ISO
Windows Server 2025 DHCP v2.ISO
```

## Hostname

After your installation, immediately adapt the Hostname.
If using the Windows Server 2025 v2.ISO - File the Default Hostname will be unreadable.

(* Note: When using the preconfigured DHCPv2.ISO - File, this Step is not necessary.)

## Networkadapter Configuration

It is important that your Domain Controller utilizises <strong>two</strong> Network Adapters.
One Adapter has to be <strong>ALWAYS</strong> on the Status:

```
"NAT"
```
Your second Network adapter has to be adjusted to for the upcoming DHCP Configuration and the associated new "Network".

To configure the second Network Adapter, head over into the Server Manager:

```
Server Manager > Configure Local Server > Network Adapters > Network Adapter 3 (Note, that the Number might differ!)
```
It will open up the Network Adapter Options. Disabling IPv6 is optional.
Configure the Adapter to use the following IP-Address, Subnetmask and DNS-Server:

```
IPv4-Address: 192.168.0.254
Subnetmask:   255.255.255.0
DNS-Server (Primary): 127.0.0.1 (Local Host or just use the static IPv4 Address again)
```

> ℹ️ **Info**
> Domain Controllers <strong>ALWAYS</strong> need to have their own IP-Address configured as the primary DNS-Server.  
> This ensures that Active Directory clients can properly locate and authenticate against the Domain Controller.  
> Without this setting, replication, Group Policy updates, and client logons may fail because DNS lookups would not resolve correctly.

## Installing Services

For the Assessment, no Roles & Features have been pre-configured. To install and configure the required Packages head over into the Server Manager again and do the following:

```
Server Manager > Manage > Add Features and Roles
```

Then select the following Features:

```
- Active Directory Domain Services
- DNS-Server
- DHCP-Server
```

## AD Configuration

To finalize the AD-Setup, hit the yellow Marker within the Server Manager. This will open up the current progressbar. If the AD Services are finished you will see "Promote to Domain Controller". Click this and do the following within the Setup Wizard:

```
> Select the deployment operation: Add a new forest
  Domain: schule.local

> Enter a Password for the Domain. In our case this might actually be a very easy Password for example: Server123!
```

## DHCP Configuration

The goal of the Assessment is, to successfully add a Client into your Domain. For the IP-Addresses to not conflict with the school IP-Blocks and intern DHCP-Servers, select DHCP-Service Feature within the Server Manager.

Then do the following steps:

```
- schule.local
  - 192.168.0.254 (eins)
    - Bereich [...]

Select the default Bereich and delete it. Create a new one by right clicking on the Domain Root.
```

Now the tricky part:

```

```