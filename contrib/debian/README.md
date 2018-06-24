
Debian
====================
This directory contains files used to package xandod/xando-qt
for Debian-based Linux systems. If you compile xandod/xando-qt yourself, there are some useful files here.

## xando: URI support ##


xando-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install xando-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your xandoqt binary to `/usr/bin`
and the `../../share/pixmaps/xando128.png` to `/usr/share/pixmaps`

xando-qt.protocol (KDE)

