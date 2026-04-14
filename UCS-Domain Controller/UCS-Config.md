# UCS Initial Configuration

## Basis Setup

After importing the .OVA, set the forgein Language to `Deutsch` and location to `Mannheim`.
Follow through the Setup Wizard and choose `New Domainforest`.

## Domain root
In order to create the according Domain, delete the default recommended Domain and replace it with `ucs-dc.schule.local`.

## IP-Config

For the UCS Domain Controller use the IP Address schema `10.16.<Roomnumber>.<PC Number +200>`.
Set the Gateway to the default schools GW `10.16.1.245`.

**Do NOT** interfere the DNS Setup by changing it to `127.0.0.1` yet!

## Required Applications
After the successfull Setup and Reboot of the Domain Master, head over into the UMC (Universal Management Console) of your UCS Master.
This can be accessed via `https://<UCS-DC IP Adress>`.

Login with the Default Login Credentials `Administrator` & `<Your Domain Password`.

Switch into the App Center and search for `Active Directory Connection` and install it.
This process will take a while, due to the fact that with this specific package,the following two packages will automatically be installed at the same time `Active Directory Take Over` & `Active Directory Compatible Domain Controller`.

## Client Setup

Now we are ready to configure the AD client. Head over into the Client-Config.md File for this specifically.
