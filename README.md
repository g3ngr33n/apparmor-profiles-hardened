# About Apparmor-Profiles-Hardened

I decided to make a repo git for this project to share my profiles apparmor outside my overlay Gentoo, since most of the profiles available doesn't give the best restriction that apparmor offer.
I hope to help folks looking for updated and hardened profile, feel free to contribute or give any feedback. 

# Why hardened profiles

Apparmor is great security module available on the Linux, it offer a simple way to enforce mandatory access control over your application. Apparmor is a no brainer if you are looking for a
serious security layer, unfortunately it is often missued and basic profiles, made to work out of the box on every distribution are applied, which offer a very low security layer.

The cost of hardening your application often require to break / restrict certains functions or features, this is a normal behavior.  However, as Apparmor is totaly flexible, you have the control of the restriction. 


# Contribution welcome

If you feel to share, make a PR ! I will as much as I can take in consideration any request or advise, if you want to convert those profile for your distribution, please do ! 
if you need help, have question or an issue with those profiles, open an issue on this git.


# Documentation work in progress

If you are looking for a good documentation on apparmor, you should add the official wiki your bookmark

[Apparmor documentation](https://gitlab.com/apparmor/apparmor/wikis/Documentation)

The profiles offered here was made from scratch, the idea behind it is explained here :

[Profiling by hand]https://gitlab.com/apparmor/apparmor/wikis/Profiling_by_hand)

I aim to share later on, some of my method to write a minimal restricted profile for apparmor.


## Copyright

Apparmor is under GNU/GPL v2 license
Official url : https://gitlab.com/apparmor/apparmor
