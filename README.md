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

### Advanced Package Tool (APT)

#### Installing a new package

```console
sudo apt install mysql-server
```

#### Cleaning the cache

APT maintains a package cache where it stores DEB files it has downloaded and installed.

This usually lives in */var/cache/apt/archives* and can sometimes take up many hundreds
of megabytes on the computer.

You can have APT clean out the package cache by running the following command, which deletes all the cached DEB files.

```console
apt clean
```

Alternatively, you can run  the following command, which deletes cached DEB files that are beyond a certain age and keeps newer packages.

```console
apt autoclean
```

#### Removing packages

```console
apt remove [package name]
```

To remove configuration files along with the package (both commands do the same)

```console
apt remove -purge [package name]

apt purge [package name]
```
