Ansible Role: docbuilder
=========

Build status for this role: [![Build Status](https://travis-ci.org/PeterMosmans/ansible-role-docbuilder.svg)](https://travis-ci.org/PeterMosmans/ansible-role-docbuilder)

This role installs the docbuilder toolchain, to create PenText reports. See https://github.com/radicallyopensecurity/pentext and https://pentext.org/ for more information on PenText.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below:


**fop_version** : The version of fop that will be installed. The default can be found in `defaults/main.yml`.
```
fop_version: 2.1
```



**docbuilder_saxon_files** : The source location of the saxon binaries. The default can be found in `defaults/main.yml`..
```
docbuilder_saxon_files:
  - src: https://downloads.sourceforge.net/project/saxon/Saxon-HE/9.7/SaxonHE9-7-0-6J.zip
```



**docbuilder_saxon_files** : The source location of the fop binaries. The default can be found in `defaults/main.yml`..
```
docbuilder_fop_files:
  - src: https://archive.apache.org/dist/xmlgraphics/fop/binaries/fop-{{ fop_version }}-bin.zip
```


Dependencies
------------

None.

Example Playbook
----------------

```
- hosts: all
  become: yes
  become_method: sudo
  roles:
    - role: PeterMosmans.docbuilder
```


License
-------

GPLv3

Author Information
------------------

Created by Peter Mosmans. Feedback always appreciated.
