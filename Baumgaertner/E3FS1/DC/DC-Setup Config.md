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

Server Manager > Local Server > Ether2

When adapting the Config, choose 192.168.1.0/24 as Network.
Under IP-Address use 192.168.1.1 and as Subnetmask 255.255.255.0.
For the DNS Services, a DC ALWAYS has to use his own Address as DNS Server in order to properly work as DC and DNS Server for new Clients within the AD.

## Client Configuration

### ISO Version

For the Windwos Test Client, use the "Windows-10-packettracer" Version.

### Client Network Configuration

In Order for the Client to be successfully integrated into your Domain, configure both or the single Networkadapter and change it to "intern Network".
Afterwards you will be prompted to accept or decline Network Detection. Click "YES". For foolproof concepts, disable all Firewalls.

### Registering Client in AD

Under "Win-Key > Workgroup" and adapt the Workgroup. Switch it to Domain and enter "schule.local".

If successfull you will be prompted with the AD Login. Use the DC Admin Account and credentials here.
