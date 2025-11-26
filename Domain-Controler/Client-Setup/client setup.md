# Setup Guide - AD Client

## ISO-File

For the test AD Client we will use the Windows 10 Wireshark Client ISO File.

## Changing the Network Adapter Status

In order to get no issues with connecting onto your AD, change the default status

```
"NAT"
``` 
for the Clients Adapter to

```
"Intern Network"
```

After the Client is up, it will ask you if you wish to be discoverd within the Network. 
Accept this, otherwise the standard Windows Firewall will block your AD Logon requests.

## Adding the Client to the AD

Use the search and search for

```
Windows Workgroup
```

Then switch to Domain and enter 

```
school.local
```

If the connection is successfull it will prompt you to login. Use the credentials you have used for the DC-Server Setup 

```
User: .\Administrator
PW:   Server123!
```
After a while you will be greated with "Welcome to your Domain". Reboot the Client and switch over to the Domain Controller. Use "F5" to refresh the DHCP-Management UI. 

Open the Active Directory Users & Computers UI. Navigate to Computers and you should be able to see your Client within this folder.

## Issues and Solutions

1) You have denied Network search

```
> Disable the Firewall Profiles (* Note: ALL have to be disabled, not just Domain to minimize further fail-states.)

```

2) Network Adapter not configured

```
If you have Network issues, check wether your Client Network Adapter is correctly set to "Intern Network" or if it is still set to "NAT"
```