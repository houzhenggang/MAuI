% Massive automated installation of complete Linux images - MAuI
% 2014-11-11
% Cem

Concept
-------

The basic idea is to provide a system, that allows an easy installation
of preconfigured Linux images on multiple target computers.

The system consists of a modified Arch Linux live medium, that will run
as a standalone server. The target computers shall be connected to this server
via Ethernet. These target machines are then booted over this LAN 
connection[^1]. And their new system is installed, based on the preconfigured 
image.

[^1]: For most computers a setting is configurable in the BIOS. Look for: 
"Boot via Ethernet" or "PXE".

At this point the image, that shall be installed, has to be ready.
Though, some requirements for the images will probably have to be met, 
the process of creating and maintaining preconfigured images is kept
separately. Instructions and maybe tools for this might be provided as well.

Additionally to the live medium a storage medium for the images is
required, e.g. an external hard disk drive.

Using an external storage has several advantages. It facilitates the process 
of creating an image from an existing installation. And it's flexible in terms 
of size and mobility.

A live medium was chosen because it's by far the simplest way to turn 
an ordinary computer into an installation server and again, this provides
a maximum of flexibility in terms of mobility. If necessary, the live 
medium can be adapted and recreated. By basing it on Arch Linux, we rely 
on a proven and expandable method to create a custom live medium[^aiso].

[^aiso]: From the Archiso wiki article: "Simply put, if it involves Arch 
on a shiny coaster, it can do it." - https://wiki.archlinux.org/index.php/Archiso

And finally, images were chosen because they make it possible to simply make
the wished configuration and system adaptions on a running system[^2].
This saves you off the PITA of scripting these changes for an automated
installation. The drawback is that driver recognition cannot be done for 
the target machines during installation and the images have to be kept
up to date.

[^2]: Though, this system might actually be on a virtual machine.



Implementation
--------------

### Adaptions to the Arch Linux live medium

