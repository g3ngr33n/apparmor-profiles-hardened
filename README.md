# About Apparmor-Profiles-Hardened

I decided to make a repo git for this project to share my profiles apparmor outside my overlay Gentoo, since most of the profiles available doesn't give the best restriction that apparmor offer.
I hope to help folks looking for updated and hardened profile, feel free to contribute or give any feedback. 

# Why hardened profiles

Apparmor is great security module available on the Linux, it offer a simple way to enforce mandatory access control over your application. Apparmor is a no brainer if you are looking for a
serious security layer, unfortunately it is often missued and basic profiles, made to work out of the box on every distribution are applied, which offer a very low security layer.

The cost of hardening your application can require to break / restrict certains functions or features of your application, however, as Apparmor is totaly flexible, you always have the choice to relax the control
access if you wish or have the need of it.
 
# What are the profiles available ?

As for today, 3 profiles which include : Firefox 60.4, Torbrowser 8.04 and KeepassX , profile was tested on apparmor 2.12.1, 2.13.1 and higher. Those aren't final and subject to change anytime.
 
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
* [Firefox](configuration hardening : https://github.com/pyllyukko/user.js/)
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

# Keep in mind

As apparmor is a great security module, It's doesn't make your system bullet proof against nasty exploit that will compromise the Linux kernel, fortunatelly those are rare ###### (publicly at least)

Security is vast and complex subject, where every thing you read aren't always as good as they sound, however, in addition of those profile, if you didn't do it already, make a simple sandbox 
as describe here :[Simple sandbox](https://wiki.gentoo.org/wiki/Simple_sandbox), for each appplication.

It took 1 minute to setup, it is not a Gentoo feature. It will work out of the box in your Linux system.

# Contribution welcome

If you feel to share, make a PR ! I will as much as I can take in consideration any request or advise, if you want to convert those profile for your distribution, please do ! 
 If you need help, have question or an issue with those profiles, open an issue on this git.

# Documentation work in progress

If you are looking for a good documentation on apparmor, you should add the official wiki your bookmark

[Apparmor documentation](https://gitlab.com/apparmor/apparmor/wikis/Documentation)

The profiles offered here was made from scratch, the idea behind it is explained here :

[Profiling by hand(]https://gitlab.com/apparmor/apparmor/wikis/Profiling_by_hand)

I aim to share later on, some of my method to write a minimal restricted profile for apparmor.


## Copyright

Apparmor is under GNU/GPL v2 license
Official url : https://gitlab.com/apparmor/apparmor
