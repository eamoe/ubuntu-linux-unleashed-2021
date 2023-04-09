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
