# Backup and Restore Configuration

## Scenario 1: Backing Up Configuration from a Switch or Router Using TFTP

**Server**

```cmd
c:\> ipconfig 192.168.1.2 255.255.255.0 192.168.1.1
# Enable TFTP service
```

**Router | Switch**

```cmd
> enable
# copy running-config tftp
Address or name of remote host []? 192.168.1.2
Destination filename [Router-config]? my-config
# exit
```

## Scenario 2: Restoring Configuration from a Switch or Router Using TFTP

**Server**

```cmd
c:\> ipconfig 192.168.1.2 255.255.255.0 192.168.1.1
# Enable TFTP service
# Put your configuration file into TFTP server
```

**Router | Switch**

```cmd
> enable
# copy tftp: flash:
Address or name of remote host []? 192.168.1.2
Source filename []? my-config
Destination file name [my-config]? // Press enter if you don't want rename file
# exit
```

To ensure your configuration file has been downloaded to the Cisco device, use the following command: `#show flash`


```cmd
# show flash
System flash directory:
File  Length   Name/status
  3   486899872isr4300-universalk9.16.06.04.SPA.bin
  4   659      my-config
  2   28282    sigdef-category.xml
  1   227537   sigdef-default.xml
[487156350 bytes used, 2761893250 available, 3249049600 total]
3.17338e+06K bytes of processor board System flash (Read/Write)
```
