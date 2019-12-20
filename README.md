# About Apparmor-Profiles-Hardened

I decided to make a repo git for this project to share my profiles apparmor outside my overlay Gentoo, since most of the profiles available doesn't give the best restriction that apparmor offer.
I hope to help folks looking for updated and hardened profile, feel free to contribute or give any feedback. 

# Why hardened profiles

Apparmor is great security module available on the Linux, it offer a simple way to enforce mandatory access control over your application. Apparmor is a no brainer if you are looking for a
serious security layer. Common profiles shipped with apparmor are made to work out of the box, security provided by those are very low to none.

# How hardened profiles

By appling a simple method : The more a profile restrict access and permission of a software (read, write, memory map, link lock, signal...)
the less it become possible to exploit bugs/vulnerability to gain access / privilege to the system. 

Let's take the example of a common browser, such as Firefox, a great number of functions / options offered are unknown
or not useful for the usage you have of it. If disk space, processor or memory wasted by those aren't a major concern, 
weaken in a best case the security of the system to the total exposure of it is a parameters to be aware of.

Apparmor give you a the control of what the software can and cannot do beyond his own functionality : it
doesn't fix vulnerability but can prevent them to work.

# Documentation work in progress

If you are looking for a good documentation on apparmor, you should add the official wiki to your bookmark

[Apparmor documentation](https://gitlab.com/apparmor/apparmor/wikis/Documentation)

The profiles offered here was made from scratch, the idea behind it is explained here :

[Profiling by hand]https://gitlab.com/apparmor/apparmor/wikis/Profiling_by_hand)

## Copyright

Apparmor is under GNU/GPL v2 license
Official url : https://gitlab.com/apparmor/apparmor
