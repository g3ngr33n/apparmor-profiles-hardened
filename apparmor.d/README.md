## Firefox

By default, Firefox is shipped for maximum user experience but it come with a cost of a low security and maximum private data collection. If the previous version of Firefox was more or less easy to configure to increase the security 
and block all harmful privacy invasion, it has become a hassle, changing the settings for all those privacy sucker in the about:config doesn't seem to be respected anymore. 

This profile was made with security/privacy in mind, it does :

* Disable Safebrowsing, Telemetry, Aufofill, Followonsearch, Activity stream, Data reporting, Pocket and all those features.
* Firefox read permission is restricted, cannot browser trought your system *exmaple in your urlbar : /home or /usr....*
* Addon/Extension installation restricted, extensions cannot  be installed as long apparmor is enabled. *You can of course temporary disable apparmor for install your extensions*
* Downloads restricted 
* Html5 video restricted 
* Disable Webgl, Webrtc and other features harmful for the security.
* Denied access to your graphics gpu, memory usage and other hardware ressources of your machine

Consider to add the following hardening project for more security 

* [Simple sandbox](https://wiki.gentoo.org/wiki/Simple_sandbox)
* [Firefox configuration hardening](https://github.com/pyllyukko/user.js/)
* [uMatrix](https://github.com/gorhill/uMatrix )

*Firefox will not start if no profile are already available (.mozilla/firefox .cache/mozilla ...), run first firefox with apparmor disabled to create the basic directory / configuration file / cache... required.*


## Torbrowser

- torbutton plugins and noscript are now working
- Average restriction compare to Firefox but shouldn't broke any sensitive settings made by Torbrowser

Consider to set Safest level in the Security settings of the torbutton or set javascript.enabled to false in about:config

*Torbrowser will not start if no profile are already available (.mozilla/torbrowser .cache/mozilla ...), run first torbrowser with apparmor disabled to create the basic directory / configuration file / cache... required.*


## Keepassx

- Network access disabled 
- Written for Qt5.x <
- All features are working

*Small issue, When you select Open database, the dialog will show your currrent directory / home as empty, simply enter in the input field "File name" your database name to open it.*


## Pulseaudio

Custom profiles fit for my needs

- Network access, webrtc... disabled
- Allow pulseaudio to forward sound from pcm to hdmi
