# Installing Microsoft Office 2010, 2013, and 2016 on Linux
By using only
- Microsoft Office VL .iso files
- wine
- winbind
- winetricks

All of these are done on KDE 6 Kubuntu. I don't know how it is regarding other DEs or distros.

***

## 1. Getting the .iso files
Now I can't tell you where to get one. It's not like you can just get any _free media_ online and then goes '_heck yeah_!'. You'd be in big _mess_, _grave_ danger even.

After getting one, mount it. There will be a setup.exe file.


## 2. Install wine, winbind, and winetricks
On Debian-based,
```
sudo apt update
sudo apt install wine winbind winetricks
```
and then run the setup.exe using wine.
```
cd /path/to/file
wine setup.exe
```

**For Office 2013 and 2016, you might be told to enter an activation key.**
Simply run `winecfg` and set the Windows version to Windows 7.


## 3. Proceed the installation normally
You can proceed normally from now on.

***

## Current Issue
These are the issues I'm currently having:

- PowerPoint 2010 doesn't work, so does the 2013 and 2016 with the error "There's not enough memory or system resources to start PowerPoint".
- Office 2013 and 2016 doesn't run as smooth as Office 2010.

***
Last updated 22/2/26
