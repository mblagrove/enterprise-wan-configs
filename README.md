# Network Notes

## VLANs

### Arista
```
# show run | section vlan

vlan 10,20,30,40
interface Ethernet2
   switchport access vlan 20
interface Vlan10
   ip address 10.1.10.1/24
interface Vlan20
   ip address 10.1.20.1/24
interface Vlan30
   ip address 10.1.30.1/24
interface Vlan40
   ip address 10.1.40.1/24
mac address-table static 0050.7966.6854 vlan 10 interface Ethernet2
```

#### Assign Password
```
username admin secret <password>
```

#### Port Security Violation Mode
```
#switchport port-security violation shutdown
#errdisable recovery cause portsec
```

#### Port Security
#show port-security address
```
!
mac address-table static 0050.7966.6854 vlan 20 interface Ethernet2
!
mac address-table static 0050.7966.6855 vlan 20 interface Ethernet3
!
mac address-table static 0050.7966.6856 vlan 20 interface Ethernet4
```

```
#show errdisable recovery
   Errdisable Reason              Timer Status   Timer Interval
------------------------------ ----------------- --------------
   acl                            Disabled                  300
   arp-inspection                 Disabled                  300
   bpduguard                      Disabled                  300
   dot1x-coa                      Disabled                  N/A
   dot1x-session-replace          Disabled                  300
   fabric-link-failure            Disabled                  N/A
   fabric-link-flap               Disabled                  N/A
   hitless-reload-down            Disabled                  300
   lacp-no-portid                 Disabled                  N/A
   lacp-rate-limit                Disabled                  300
   license-enforce                Disabled                  N/A
   link-flap                      Disabled                  300
   no-internal-vlan               Disabled                  300
   portchannelguard               Disabled                  300
   portsec                        Enabled                   300
   stp-no-portid                  Disabled                  N/A
   tapagg                         Disabled                  300
   uplink-failure-detection       Disabled                  300

```
### Juniper
Disabled auto upgrade messages annoying 
First login command `cli`
#### VLANs
```
set vlans VLAN10 vlan-id 10
set vlans VLAN20 vlan-id 20
set vlans VLAN30 vlan-id 30
set vlans VLAN40 vlan-id 40
```


