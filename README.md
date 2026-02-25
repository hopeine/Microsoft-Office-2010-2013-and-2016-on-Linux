<img width="1920" height="1080" alt="Office-test" src="https://github.com/user-attachments/assets/524ed7c9-d5b1-4b67-add8-51a424905191" />

# Installing Microsoft Office 2010, 2013, and 2016 on Linux
A guide to installing Microsoft Office on Linux without any VMs or Wine Managers.

The requirements are the following:
- Microsoft Office VL .iso files
- wine
- winbind
- winetricks

Tested on Kubuntu with KDE 6 and wine-10.0. Should work on other distros/DEs/wine versions. Feel free to try.

***

## 1. Getting the .iso files
Now I can't tell you where to get one. It's not like you can just get any _free media_ online and then go '_heck yeah_!'. You'd be in big _mess_, _grave_ danger even.

After getting one, mount it. There will be a setup.exe file.

## 2. Install wine, winbind, and winetricks
On Debian-based systems,
```
sudo apt update
sudo apt install wine winbind winetricks
```
and then run setup.exe using wine.
```
cd /path/to/file
wine setup.exe
```

### For Office 2013 and 2016, you might be told to enter an activation key.
Simply run `winecfg` and set the Windows version to Windows 7.

## 3. Proceed the installation normally
You can proceed normally from now on.

***

## Notes

### Fonts differ; bullet list not rendered properly and shown as square.
If bullet lists show as squares, Wine probably can't find the right font files (`.ttf`). Fix this by installing it from winetricks.
`winetricks corefonts` or `winetricks allfonts`.

Or if you have Windows installed, copy the fonts from `C:\Windows\Fonts` to `~/.wine/drive_c/windows/Fonts`. You may copy all the fonts, or just the following:
- Arial
- Calibri
- Courier New
- Times New Roman
- Symbol (This fixes the bullet list problem)
- Wingdings
- Webdings
- etc.

### Right-clicking in a document results flickering.
Maybe because you're on Wayland. Weirdly enough though, after I installed X11, it doesn't flicker anymore even if I'm on Wayland. Maybe some X11 dependencies fixed the problem.


## Current Issue
These are the issues I'm currently having:

- PowerPoint 2010 doesn't work, so does the 2013 and 2016 with the error "There's not enough memory or system resources to start PowerPoint".
- Office 2013 and 2016 doesn't run as smooth as Office 2010.

If resolved, I might put the solutions into the Notes section.
