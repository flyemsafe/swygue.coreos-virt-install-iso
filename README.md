Role Name
=========

This role does the following:

 * Downloads these coreos files:
     - metal-bios.raw.gz
     - *.iso
 * Copy over your ignition files for worker, bootstrap and master to the directory to be exported as a podman volume
 * Extract the coreos iso and copy the efiboot.img, initramfs.img and vmlinuz to /tmp/coreos
 * copy over treeinfo to /tmp/coreos
 * build a podman httpd container and start it

Requirements
------------

This role requires you ignition files. It's meant to be used with https://github.com/RedHat-EMEA-SSA-Team/hetzner-ocp4.

Role Variables
--------------

These variables need values:

```
admin_user: your_username
downloaded_files_dir: downloaded_files_and_podman_volume
```

Dependencies
------------

none

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
