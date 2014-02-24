#############################
 Remote Secure Shell Sessions
#############################

.. Warning::

   This article includes proprietary information about AAltSys logins. Please 
   generalize this material before release::

     Identify username _____________________________________,
     registration __________________________________________,
     LTSP server IP ________________________________________.

Command line usage
=============================

Basic::

  ssh -l [username] [registration].servers.aaltsys.net

NX Port forwarding of LTSP server::

  ssh -L8889:ltspserver:8888 -l [username] [registration].servers.aaltsys.net

Gnome terminal
=============================

X-11 Forwarding with gnome-terminal (default IP for ltspserver is 10.4.0.2)::

  gnome-terminal -x ssh -L8889:ltspserver:8888 -l [username] [registration].servers.aaltsys.net

Fixing Changed SSH Keys
=============================

When using :command:`ssh` from a terminal icon or weblink, the session may 
abort when starting. The most likely cause for this is a change to the ssh 
key. To address the problem for a terminal icon, open a terminal shell prompt:: 

  ssh [registration].servers.aaltsys.net

Address this problem for a weblink::

  ssh://[registration].servers.aaltsys.net/

The line number in your :file:`~/.ssh/known_hosts` file which is wrong will be 
displayed. Delete this line with the command::

  sudo sed -i c\[linenumber] ~/.ssh/known_hosts