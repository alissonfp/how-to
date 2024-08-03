~~~sh
systemclt status NetworkManager

nmcli conn show

nmcli conn add type vlan con-name vlan12 dev ens160 id 12 connection.autoconnect yes

nmcli conn modify vlan12 ipv6.method "disabled"

nmcli conn modify ens160 connection.autoconnect no

nmcli conn modify ens160 ipv6.method "disabled"

nmcli conn modify ens160 ipv4.method "disabled"

ip a
