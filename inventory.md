# Inventory

Lists all devices part of the home lab.

I'm having fun using names inspired to Norse mythology.

## Networks

### Constraints

- Have the name of a Norse realm.
- Use 10.x0.x0.0/24 as network
- Reserve 10.x0.x0.x0 to the gateway
- Reserve from 10.x0.x0.x0 to 10.x0.x0.x9 for network nodes
- Reserve from 10.x0.x0.100 to 10.x0.x0.199 for hosts
- Reserve from 10.x0.x0.200 for static routes and special cases
- Not assign any other range.

### Table

| Name         | Type                  | CIDR /24   | Gateway    | Description              |
| ------------ | --------------------- | ---------- | ---------- | ------------------------ |
| Midgard      | Unique Wired Wireless | 10.10.10.0 | Jormungand | Internet access          |
| Jotunheim    | Unique Wireless       | 10.20.20.0 | Loki       | Italian gateway access   |
| Muspelheim   | Virtual Wired         | 10.30.30.0 | Surtr      | Public services          |
| Niflheim     | Virtual Wired         | 10.40.40.0 | Hel        | Private services         |
| Alfheim      | Virtual Wired         | 10.50.50.0 |            | Private virtual network  |
| Svartalfheim | Virtual Wired         | 10.60.60.0 |            | Private virtual network  |
| Nidavellir   | Virtual Wired         | 10.70.70.0 |            | Private virtual network  |
| Asgard       | Unique Wired Wireless | 10.80.80.0 | Borr       | Private physical network |
| Vanheim      | Unique Wired Wireless | 10.90.90.0 | Njoror     | Private physical network |

## Hosts

### Modi

Used to test Ymir bare metal OS.

VirtualBox VM within Thor.

### Thor

Workstation  

Windows:
- Firefox
- Visual Studio Code  
&nbsp;

WSL Ubuntu:
- Git
- GPG

### Ymir

Home lab.