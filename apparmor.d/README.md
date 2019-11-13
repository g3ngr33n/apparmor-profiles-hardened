## Virt-viewer (remote-viewer)

Graphical client for spice-gtk, it has since Qemu 4 add a new display option (-display spice-app), offering the
spice feature like the mouse passtrought guest <-> host. The interface look similar to the gtk display (-display gtk)

Starting from the version 0.36, spice-gtk has decided to be hard dependent of gstreamer, gstreamer-audio, gstreamer-plugins (full list https://gitlab.freedesktop.org/fziglio/spice-gtk)
while Qemu can be build without it.

Despite the evident lost of performance for the Qemu system build without all those new dependency,
It's increase the surface attack : https://www.cvedetails.com/cve/CVE-2019-9928/

This profile disable those dependency (including libgstrtsp.so :-)), here the output of a running qemu system :

https://github.com/g3ngr33n/apparmor-profiles-hardened/tree/master/extra/spice-gtk.log

## Waterfox

* Addon/Extension installation restricted, extensions cannot  be installed when apparmor is active
* Downloads restricted
* Html5 video restricted
* Disable Webgl, Webrtc and other features harmful for the security.
* Denied access to your gpu, memory usage and other hardware ressources of your machine

Consider to add the following hardening project for more security 

* [Simple sandbox](https://wiki.gentoo.org/wiki/Simple_sandbox)
* [Firefox configuration hardening](https://github.com/pyllyukko/user.js/)
* [uMatrix](https://github.com/gorhill/uMatrix )

## Psi

Psi IM is a good example of security minded development. Light, fast, rich in features but not fancy, slow development. This profile restrict the
the sound access and possibly some other features which I don't use.

Few extra plugins of psi+ have been installed as :

* [Off-the-Record](https://otr.cypherpunks.ca/)
* [Omemo](https://conversations.im/omemo/)
* [Psi skins plugin](https://github.com/psi-im/plugins/blob/master/generic/skinsplugin/skinsplugin.cpp)


## Pidgin (outdated)

Pidgin is a nice IM client with a lot of features, but it has fat code. Except Jabber, it allow with third party plugins, a lot of protocol from irc to skypeweb, steam messenger and other plugins that
require access to sensitive part of the os, definitevely the kind of application that need tight control.

Tested wtih xmpp/jabber with the plugins OTR and lurch (OMEMO).

Build with minimum :
gtk nls pie -aqua -dbus -debug -doc -eds -gadu -gnutls -groupwise -gstreamer -idn -meanwhile -ncurses -networkmanager -perl -prediction -python -sasl -silc -spell -tcl -tk -xscreensaver -zephyr -zeroconf

- Plugins (OTR, lurch) work
- Restricted access to sound system
- Restricted access to file system
- Restricted file transfer,
- Gstreamer disabled
...

## Firefox

![Fireproc ](https://raw.githubusercontent.com/g3ngr33n/apparmor-profiles-hardened/master/ffisdead.gif)

No longer maintained

## Torbrowser

Following the bulimia of Firefox. No longer maintained.
