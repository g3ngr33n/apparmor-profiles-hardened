## Virt-viewer (remote-viewer)

Graphical client for spice-gtk, the profile was written for spice-gtk-0.35 with some custom patch, including :

- qmp support
- fix of the cve 2020-14355

Full list of patch : https://github.com/g3ngr33n/emergeless/tree/master/net-misc/spice-gtk/files

### Short story for spice-gtk:

Starting from spice-gtk-0.36, the gnome team sponsored gstreamer became mandatory removing all other video decoder / image compression (mjpeg...). Some time later the automatic resize of the window was changed to work only for gnome-shell (https://bugzilla.xfce.org/show_bug.cgi?id=15897). 

remote-viewer is used separetely of the qemu daemon (socket connection remote-viewer spice+unix:/) with chardev spiceport org.qemu.monitor.qmp.0 (Giving the control of power off / reset or pause on the virtual system) and virtserialport com.redhat.spice.0 (allow mouse passtrough host <-> guest)

## Qemu

Work in progress

## bin.rm

Common apparmor profile are denying everything unless you explicitly give it permission. 

Since apparmor 3, you can now write a profile doing the reverse, everything is allowed unless you explicitly deny it permission, I made a fast example with bin.rm 