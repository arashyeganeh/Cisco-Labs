# Telnet Configuration

## Scenario 1: Enable Telnet on a Router

* Enable Telnet on the router

* Set a password for Telnet access

* Connect to the Cisco device using Telnet

**Router**

```bash
> enable
# configure terminal
(config)# interface gigabit 0/0/0
(config-if)# ip address 192.168.1.1 255.255.255 0
(config-if)# no shutdown
(config-if)# exit
(config)# Line vty 0
(config-line)# transport input telnet
(config-line)# password p@ssw0rd
(config-line)# exit
(config)# exit
# write
```

**PC**

```cmd
c:\> ipconfig 192.168.1.2 255.255.255.0 192.168.1.1
c:\> telnet 192.168.1.2 /* The password is pa@ssw0rd */
```



