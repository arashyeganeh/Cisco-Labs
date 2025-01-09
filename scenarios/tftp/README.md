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
# copy tftp: running-config
Address or name of remote host []? 192.168.1.2
Source filename []? my-config
Destination file name [my-config]? // Press enter if you don't want rename file
# write
# exit
```
