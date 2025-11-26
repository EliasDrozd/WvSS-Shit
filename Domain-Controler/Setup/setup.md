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

## Netadapter Configuration

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
