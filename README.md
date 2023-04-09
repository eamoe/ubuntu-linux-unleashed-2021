# Ubuntu Linux Unleashed 2021

## Installing Ubuntu and Post-Installation Configuration

### Shutting Down

Shut down the system by command
```console
sudo shutdown -h now
```

### Restarting the system

To restart the system
```console
sudo shutdown -r now
```

### Updating & upgrading the system

Tell the package management utility *apt*
to check the Ubuntu repositories
and look for any updates to the installed software
```console
sudo apt update
```

Next, upgrade the software by entering the following:
```console
sudo apt full-upgrade
```

For a production server, the option *upgrade* (instead of *full-upgrade*)
might be a better choice because *upgrade* does not make major changes to software installations.

### Setting the time and date

To see Linux system's current date and time
```console
date
```

To change date & time (month, day, hour, minute, and year)
```console
sudo date 092810332021
```

To see hardware time & date
```console
sudo hwclock --show
```

To manually set the hardware clock
```console
sudo hwclock --set --date "09/28/21 10:33:00"
```

To set the system time from PC's hardware clock
```console
sudo hwclock --hctosys
```

To set hardware clock using the system time
```console
sudo hwclock --systohc
```
