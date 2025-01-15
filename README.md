# Flatpak-trash-remover
Flatpak apps store all their data (if they are made well) in `~/.var/app/org.APP.NAME`. Those folders may stay after uninstallation, as you need to use `flatpak uninstall --delete-data APP`. GUI Software stores have a dialog, but you may still miss it.

This tool searches for appdata folders where there is no matching app, and prompt you to remove it.

Install:

```
curl https://github.com/trytomakeyouprivate/Flatpak-trash-remover/raw/main/flatpak-trash-remover -o ./flatpak-trash-remover
run0 sh -c '
  mkdir /var/usrlocal/bin || mkdir /usr/local/bin 
  mv ./flatpak-trash-remover /var/usrlocal/bin
  chown -R root:root /var/usrlocal/bin
  chcon -R system_u:object_r:bin_t:s0 /var/usrlocal/bin #on SELinux systems
  chmod +x /usr/local/bin/flatpak-trash-remover
'
```

Usage:

```
~ ❯❯❯ flatpak-trash-remover

=====================================================
              Flatpak Trash Remover

Cleanup leftover folders of uninstalled Flatpak apps
=====================================================

Progress: 27/90
The app com.xnview.XnViewMP is not installed. Do you want to delete its folder? (Y/n): y
...
Progress: 90/90
All Apps checked.
```
