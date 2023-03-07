# Setting Firewall Filter
* * *
- Masuk ke winbox console
* * *

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
