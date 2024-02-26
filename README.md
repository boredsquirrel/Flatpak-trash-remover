# Flatpak-trash-remover
Flatpak apps store all their data (if they are made well) in `~/.var/app/org.APP.NAME`. Those folders may stay after uninstallation, as you need to use `flatpak uninstall --delete-data APP`. GUI Software stores have a dialog, but you may still miss it.

This tool searches for appdata folders where there is no matching app, and prompt you to remove it.

Usage:

```
wget https://github.com/trytomakeyouprivate/Flatpak-trash-remover/raw/main/flatpak-trash-remover -P ~/.local/bin
chmod +x ~/.local/bin/flatpak-trash-remover
flatpak-trash-remover
```
