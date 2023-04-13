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

#### Apt-get vs Apt command

| apt-get command                      | apt command                        |
|--------------------------------------|------------------------------------|
| ```console apt-get install```        | ```console apt install```          |
| ```console apt-get remove```         | ```console apt remove```           |
| ```console apt-get update```         | ```console apt update```           |
| ```console apt-get upgrade```        | ```console apt upgrade```          |
| ```console apt-get dist-upgrade```   | ```console apt full-upgrade```     |
| ```console apt-get remove --purge``` | ```console apt purge```            |
| ```console apt-get autoremove```     | ```console apt autoremove```       |
| ```console apt-get search```         | ```console apt search```           |
| ```console apt-get show```           | ```console apt show```             |
| ```console dpkg --get-selections```  | ```console apt list --installed``` |
| ```console apt-get purge```          | ```console apt purge```            |

#### Compiling software from source

Install the *build-essential* package to ensure that you have the tools you need for compilation

```console
apt install build-essential
```

You may also need to install *automake* and *checkinstall*

```console
apt-get autoremove automake
apt-get install automake

apt-get autoremove checkinstall
apt-get install checkinstall
```

#### Compiling from tarball

Uncompress tar file into the source directory (needs to be created in the home directory)

```console
tar zxvf packagename.tgz -C ~/source
tar zxvf packagename.tar.gz -C ~/source
tar jxvf packagename.bz -C ~/source
tar jxvf packagename.tar.bz2 -C ~/source
```

If you are not certain what file compression method was used, use the file command to  figure it out

```console
file packagename
```

Run a script to check whether all dependencies are met and whether the build environment  is correct

```console
~/source/packagename$ ./configure
```

When your configure script succeeds, run the following to compile the software

```console
~/source/packagename$ make
```

Finally, run the following

```console
~/source/packagename$ sudo make install
```

If the compilation fails, check the error messages for the reason and run the following before  you start again

```console
~/source/packagename$ make clean
```

To remove the software

```console
~/source/packagename$ sudo make uninstall
```

#### Using the Snappy package manager

To show a list of snap packages that are available to be installed

```console
snap find

snap find searchterm
```

To install a snap package

```console
snap install packagename
```

To show a list of snap packages that are currently installed

```console
snap list
```

To update a snap package

```console
snap refresh packagename
```

To remove a snap package

```console
snap remove packagename
```

To display a list of changes, such as when snaps were installed, updated, or removed

```console
snap changes
```
