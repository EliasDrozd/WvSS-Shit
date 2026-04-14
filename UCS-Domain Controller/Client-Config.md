# Client Config

## IP-Config
Initially, boot the AD Client without changing the Network Adapter **yet**!

`> Tip: use the Windows10 PacketTracer.ISO!`

Headover into the Networkadapter Configuration > Edit IPv4 and switch the IP Configuration from DHCP to manual. Same applies for the DNS Server.
For the IP Configuration of the AD Client use the following schema:

```
IPv4: 10.16.<Room Number>.<PC Number +100>
Subnetmask: 255.0.0.0 > /8 is important!
Gateway:    10.16.1.245
```
`> Optionally: Disable IPv6`

For the DNS Server applies the same rule as for a Windows based Domain Controller, that the primary DNS Server has to be the Domain Controller itself.

```
Primary DNS Server: <UCS-DC IP Adress>
```

Now save and apply the changes!

## Network Adpater Switch

Now it is important to switch over from `NAT` to `Netzwerkbrücke`.


# UCS DNS Adaptation

This is a very important change in the Networking Configuration Files
