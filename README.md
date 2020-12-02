app-sbgrid-client
=========

This Ansible role configures a shared applications directory for software packaged by the [SBGrid Consortium](https://sbgrid.org/).  It makes use of a shared NFS mountpoint and is intended for GNU/Linux workstations in a networked environment.  Presently only RHEL family distributions are supported.

Requirements
------------

An NFS mount must be set up and exported.  The set up of this NFS mount is beyond the scope of this role and should be done in another playbook/role.

Role Variables
--------------

`sb_install_target` (string) : A path to where the NFS mount containing the programs should be mounted.

`sbgrid_nfs_mount` (string) : The NFS mountpoint (in *host:path* format).

`helpdesk_email` (string) : An e-mail address for the local contact for technical issues.  Presented to end-users if there is difficulty adding SBGrid applications to the path.

Dependencies
------------

 * `app-sbgrid-server` must be run on one host in the networked environment.  The host that the `app-sbgrid-server` role is applied to will download and update packages from the SBGrid consortium.

License
-------

Revised 3-Clause BSD License
