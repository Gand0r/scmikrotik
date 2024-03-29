# Setting Firewall Filter
* * *
* * *

```
/ip firewall filter
add action=accept chain=forward dst-address-list=Bm src-address-list=\
    "BM Client"
add action=accept chain=forward dst-address-list=spreedsheet
add action=accept chain=forward dst-address-list=maps src-address-list=\
    "maps client"
add action=accept chain=forward dst-address-list=Hello \
    src-address-list=lokal
add action=drop chain=forward comment="Block Windows Update" \
    dst-address-list="windows update"
add action=drop chain=forward dst-address-list=youtube time=\
    7h-21h,sun,mon,tue,wed,thu,fri,sat
add action=drop chain=forward dst-address-list=block time=\
    7h-21h,sun,mon,tue,wed,thu,fri,sat
add action=drop chain=forward dst-address-list=games
add action=accept chain=forward src-address-list=lokal
add action=accept chain=input comment="PPTP Server" dst-port=? \
    protocol=tcp src-address-list=lokal
add action=accept chain=forward comment="allow established connections" \
    connection-state=established
add action=accept chain=forward comment="allow related connections" \
    connection-state=related
add action=accept chain=forward comment="allow ping" protocol=icmp
add action=accept chain=forward comment="allow udp" protocol=udp
add action=accept chain=forward src-address-list=lokal
add action=drop chain=forward comment="drop invalid connections" \
    connection-state=invalid
add action=add-dst-to-address-list address-list=ML \
    address-list-timeout=none-dynamic chain=forward comment="In ML" \
    dst-port=30000-30110 protocol=tcp src-address-list="boleh internet"
add action=drop chain=forward comment="Drop ML" dst-address-list=ML \
    protocol=tcp src-address-list="boleh internet"
```

# Adding Mac
* * *
* * *
```
/interface wireless access-list
add comment=WDCP interface=wlan1 mac-address=00:23:A7:EF:2B:66
add comment=WDCP interface=wlan1 mac-address=00:23:A7:EB:BC:EE
add comment=WDCP interface=wlan1 mac-address=00:23:A7:EB:50:7A
add comment=WDCP interface=wlan1 mac-address=00:23:A7:EA:E1:C2
add comment=WDCP interface=wlan1 mac-address=00:23:A7:5A:CD:08
add comment=WDCP interface=wlan1 mac-address=00:23:A7:5C:CF:B0
add comment=WDCP interface=wlan1 mac-address=00:23:A7:AF:72:13
add comment=WDCP interface=wlan1 mac-address=00:23:A7:4E:E2:A1
add comment=WDCP interface=wlan1 mac-address=00:23:A7:AF:63:60
add comment=WDCP interface=wlan1 mac-address=00:23:A7:4E:FF:EF
add comment=WDCP interface=wlan1 mac-address=00:23:A7:5F:47:53
add comment=WDCP interface=wlan1 mac-address=00:23:A7:AF:8D:84
add comment=WDCP interface=wlan1 mac-address=00:23:A7:B5:E3:92
add comment=WDCP interface=wlan1 mac-address=00:23:A7:AF:8C:B4
add comment=WDCP interface=wlan1 mac-address=00:23:A7:B9:0C:13
add comment=WDCP interface=wlan1 mac-address=00:23:A7:AF:98:96
add comment=WDCP interface=wlan1 mac-address=00:23:A7:AF:2F:DD
add comment=WDCP interface=wlan1 mac-address=00:23:A7:5D:C4:7A
add comment=WDCP interface=wlan1 mac-address=00:23:A7:5F:44:42
add comment=WDCP interface=wlan1 mac-address=00:23:A7:B9:9A:E3
add comment=WDCP interface=wlan1 mac-address=00:23:A7:5D:34:C3
add comment=WDCP interface=wlan1 mac-address=00:23:A7:AF:56:B2
add comment=WDCP interface=wlan1 mac-address=00:23:A7:5A:D1:AD
add comment=WDCP interface=wlan1 mac-address=00:23:A7:AF:C7:38
add comment=WDCP interface=wlan1 mac-address=00:23:A7:4E:E1:B7
add comment=WDCP interface=wlan1 mac-address=00:23:A7:AF:97:95
add comment=WDCP interface=wlan1 mac-address=00:23:A7:58:DD:37
add comment=WDCP interface=wlan1 mac-address=00:23:A7:55:E4:58
add comment=WDCP interface=wlan1 mac-address=00:23:A7:4E:E2:1C
add comment=WDCP interface=wlan1 mac-address=00:23:A7:AF:14:3E
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:0D:63
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EA:EB:55
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:26:D1
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EA:E6:78
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:15:11
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:84:A6
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:A6:5E
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:B5:EE:23
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:05:65
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:6A:14
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:8C:C5
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:5C:90
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:5F:D5:90
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:B9:9C:31
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:8E:F9
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:6C:C4
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:06:A0
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:B9:9A:43
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:7F:D3
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:0D:1C
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:B9:CA:16
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EA:DE:4F
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:BE:A3
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:14:32
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:06:60
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:76:E6
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:8E:FA
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:67:BE
add comment=WDCP-CAD interface=wlan1 mac-address=88:DA:1A:06:B0:B7
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:B9:9A:46
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:2E:39
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:09:22
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:85:EE
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:5A:D1:B0
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EA:E7:D7
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:6F:9A
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:18:A2
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:BC:C6
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:8E:DF
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EA:EC:A1
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:58:D1:09
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EA:DA:F3
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:7C:32
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:5B:1F
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:B6:00:C4
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:4A:5A
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:80:59
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:9E:45
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:0E:95
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:79:63
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:64:C8
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EA:E7:33
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:2F:FB
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EB:88:5A
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:EF:1A:47
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:BF:E6
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:B1:C9
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:74:6B
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:93:DB
add comment=WDCP-CAD interface=wlan1 mac-address=88:DA:1A:06:93:F9
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:8D:7C
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:E4:30:9D
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:51:DC:2D
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:D6:10
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:B9:92:2E
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:55:AC
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:B9:92:2E
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:55:AC
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:B9:92:2E
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:55:AC
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:B9:92:2E
add comment=WDCP-CAD interface=wlan1 mac-address=00:23:A7:AF:55:AC
add comment=WDCP interface=wlan1 mac-address=9C:A5:25:FF:A1:A1
```

# Add IP Address
* * *
* * *
```
/ip address
add address=ip-mu interface=ether2 
add address=ip-mu interface=ether4
add address=ip-mu interface=ether1
```

# Add IP Firewall Filter
* * *
* * *
```
ip firewall filter
add action=reject chain=forward comment=RANSOMWARE dst-port=445 \
    protocol=tcp reject-with=icmp-network-unreachable
add action=reject chain=forward comment=RANSOMWARE dst-port=135-139 \
    protocol=tcp reject-with=icmp-network-unreachable
add action=reject chain=forward comment=RANSOMWARE dst-port=3389 \
    protocol=tcp reject-with=icmp-network-unreachable
add action=reject chain=forward comment=RANSOMWARE dst-port=445 \
    protocol=udp reject-with=icmp-network-unreachable
add action=reject chain=forward comment=RANSOMWARE dst-port=135-139 \
    protocol=udp reject-with=icmp-network-unreachable
add action=reject chain=forward comment=RANSOMWARE dst-port=3389 \
    protocol=udp reject-with=icmp-network-unreachable
add action=reject chain=forward comment=RANSOMWARE reject-with=\
    icmp-network-unreachable src-address-list=BLOCKED
add action=reject chain=forward comment=RANSOMWARE dst-address-list=\
    BLOCKED reject-with=icmp-network-unreachable
add action=reject chain=forward comment=RANSOMWARE dst-port=445 \
    protocol=tcp reject-with=icmp-network-unreachable
add action=reject chain=forward comment=RANSOMWARE dst-port=135-139 \
    protocol=tcp reject-with=icmp-network-unreachable
add action=reject chain=forward comment=RANSOMWARE dst-port=3389 \
    protocol=tcp reject-with=icmp-network-unreachable
add action=reject chain=forward comment=RANSOMWARE protocol=udp \
    reject-with=icmp-network-unreachable src-port=445
add action=reject chain=forward comment=RANSOMWARE protocol=udp \
    reject-with=icmp-network-unreachable src-port=135-139
add action=reject chain=forward comment=RANSOMWARE protocol=udp \
    reject-with=icmp-network-unreachable src-port=3389
add action=drop chain=input comment=Block_HACKED dst-address=\
    ip-provider dst-port=22,23,80,443 protocol=tcp
add action=drop chain=input comment=Block_HACKED dst-address=\
    ip-provider dst-port=22,23,80,443 protocol=udp
add action=drop chain=forward comment=RouterEDC dst-address-list=\
    !HostEDC src-address-list=RBEDC
/ip firewall service-port
set ftp disabled=yes
set tftp disabled=yes
set irc disabled=yes
set h323 disabled=yes
set sip disabled=yes
```


### To set up VLAN 75 on an Aruba 6000 switch with an IP address of 192.168.75.100 and routing to 192.168.75.254, you will need to follow these steps:

* * *
* * *

   Connect to the switch: Use a console cable to connect your computer to the Aruba 6000 switch. Then, open a terminal program on your computer to access the command-line interface (CLI) of the switch.
    
   Configure VLAN 75: To configure VLAN 75, enter the following commands:
```
(config)# vlan 75
(config-vlan-75)# name VLAN75
```
>This creates VLAN 75 and gives it a name of VLAN75.

   Configure the VLAN interface: To configure the VLAN interface for VLAN 75, enter the following commands:
```
(config)# interface vlan 75
(config-if-Vlan75)# ip address 192.168.75.100 255.255.255.0
(config-if-Vlan75)# no shutdown
```
>This configures the VLAN interface with the IP address 192.168.75.100 and enables it.

   Configure the default gateway: To configure the default gateway for VLAN 75, enter the following command:
```
(config)# ip route 0.0.0.0 0.0.0.0 192.168.75.254
```
>This sets the default gateway for VLAN 75 to 192.168.75.254.

   Configure the ports: To configure the ports for VLAN 75, enter the following commands:
   
```
(config)# interface <interface name>
(config-if)# switchport mode access
(config-if)# switchport access vlan 75
(config-if)# no shutdown
```
> Replace <interface name> with the name or number of the interface you want to configure. This sets the port to access mode, assigns it to VLAN 75, and enables it.

   Verify the configuration: To verify that the VLAN and port configurations are correct, enter the following command:   
```
# show vlan brief
```
> This command displays a summary of all configured VLANs and the ports assigned to each VLAN.

That's it! You have successfully configured VLAN 75 on your Aruba 6000 switch with an IP address of 192.168.75.100 and routing to 192.168.75.254.

    
### Reinstall WSL (Windows Subsystem for Linux), you can follow these steps:

- Open PowerShell as an administrator.
- Run the command dism.exe /online /disable-feature /featurename:Microsoft-Windows-Subsystem-Linux
- Restart your computer.
- Open PowerShell as an administrator again.
- Run the command dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
- Run the command Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform
- Download and install the latest version of the Linux distribution you want to use from the Microsoft Store.
- Launch the Linux distribution and complete the setup process.

Note: Before you proceed with reinstalling WSL, ensure that you have backed up any important data or configurations within your existing WSL installation, as this process will completely remove and reinstall WSL
