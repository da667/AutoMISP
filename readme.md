AutoMISP

a da_667 endeavor

This shell script is designed to automatically install MISP (https://github.com/MISP/MISP) and the misp-modules extension on either Ubuntu 16.04, or 18.04.

What this script does:

-Installs pre-reqs for MISP

-Installs MISP

-Configures underlying prereqs per the install guide

-Enables support for zeromq

-Installs and configures the MISP extra modules as well (https://github.com/MISP/misp-modules)

What this script does NOT do:

-It will NOT install OR configure POSTFIX. Everyone's email environment, hostname, and relay configuration differs. Configuring e-mail for MISP is an exercise left to the user.

-It will NOT create OR configure GPG. However if the user wishes to do so manually, the commands to run to generate/use GPG are included in the script, but commented out.


This script has NOT been tested on Debian or other debian-based distros, so your mileage may vary! After execution you should be left with a functional MISP installation. Please note that this script does NOT handle installation or configuration of Postfix and/or PGP key setup. Installing/Configuring Postfix for your environment is an exercise left to the user. However, the bindings required for MISP to send PGP mail are installed, and commands to generate keys, etc are commented out at lines 356-358.

Notes:

This script installs a ton of things. it'll require root or sudo access to do these things. This script sets the root mariadb password, as well as creating and setting the misp mariadb user's password. There are default passwords configured in the script, but you'll want to change them!

To do so, open up the script, and put in your password for the root user on line 11, and the misp user on line 12. As per line 9, DO NOT USE single quotes (''), double quotes (""), back ticks (``), ampersands (&), semi-colons (;) or spaces ( ) in your password -- they will break the script in fun and unique ways.

Please be aware that this script does NOT set the baseurl variable in MISP's config.php. Per documentation this doesn't really affect MISP functionality all that much. This script also sets the apache2 ServerName to [your server's hostname].local -- you'll need to modify /etc/apache2/sites-available/misp.conf and misp-ssl.conf

Questions? Thanks? Issues?

twitter: da_667

email: deusexmachina667 at gmail dot com

With thanks to:
cipherli.st for stronger SSL configuration

the MISP project maintainers for making such a great platform

infde6 for the documentation on how to install MISP on ubuntu 16.04 (https://github.com/MISP/MISP/issues/1195)

Hurricane Labs - for giving me the time to work on this.

you. for running this :D

Licensing: This project released under MIT Licensing.

Property of Hurricane Labs