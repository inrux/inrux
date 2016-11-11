## Inrux a fresh new operating system

This project is a work in progress to develop a fast microkernel OS built
from the ground up on the Rux programming language.

The concepts are intended to present an operating system development that
solves many of the security and software installation shortcomings of operating
system like Linux, BSD, and Windows while still being flexible, organized
and clean.

Some of these shortcomings include application configuration management,
application install and uninstall whether using official repositories or
just custom installing an application from the internet there are always
problems with removing these applications and managing security.

One of the goals is to present an operating system that was designed to apply
security based on resource sets like: local network access, internet access,
user interaction, software install, change display settings, impersonate another 
user, or login to the system.

### Security

A user may have a disabled login, but may still operate as a persona that
another account can impersonate.  These rights are granted by users with
sufficient privileges, but it must be granted actively, no background super
user processes can grant privileges.  A process can be granted elevated
privileges by a user, but no process can grant those privileges to another
process or user without authorization from a privileged user.  This
authorization ceases once the user login session ends or the privilege
escalation times out.  This reduces the attack vectors where a process
running with elevated privileges can give an attacker elevated privileges by
a security exploit, instead they are limited to the rights of that process only.
Since all processes run in isolation and no process is granted remote code
execution, the attacker will be denied executing anything, although the data
of that process could still be compromised.