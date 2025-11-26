# Domain Controler Setup

## ISO-Version

If applicable, choose "Windows Server 2025 DHCP v1".
When the Task is to setup the Server from ground up, use "Windows Server 2025 v1).

## DC-Master Configuration

### Hostname

On initial Startup the Hostname is "server" only, if you have chosen Option one.
If you wish to adapt it, change it via "Win-Key" > "PC-Name". Afterwards a reboot is typically required.

### Verifying DC & DHCP Server are installed

Via the Servermanager you can verify wether the required packages are installed or not.

### DNS and Testlab IP Address

In Order to allow DHCP and not creating conflicting Networks, go ahead and configure the secondary Networkadapter for your DHCP Address Pool.

Server Manager > Local Server > 
