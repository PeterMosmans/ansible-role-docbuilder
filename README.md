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



**docbuilder_saxon_files** : The source location of the fop binaries. The default can be found in `defaults/main.yml`:
```
docbuilder_fop_files:
  - src: https://archive.apache.org/dist/xmlgraphics/fop/binaries/fop-{{ fop_version }}-bin.zip
```

### FOP

The following parameters configure FOP:
**docbuilder_font_base** : The base location of the fonts. The default can be found in `defaults/main.yml`:
```
docbuilder_font_base: /usr/share/fonts/truetype/
```



**docbuilder_fonts** : A list of the fonts to be included in the FOP file. A default list can be found in `defaults/main.yml`:
```
docbuilder_fonts:
  - url: liberation/LiberationSansNarrow-Regular.ttf
    name: LiberationSansNarrow
    style: normal
    weight: normal
  - url: liberation/LiberationSansNarrow-Bold.ttf
    name: LiberationSansNarrow
    style: normal
    weight: bold
  - url: liberation/LiberationSansNarrow-Italic.ttf
    name: LiberationSansNarrow
    style: italic
    weight: normal
  - url: liberation/LiberationSansNarrow-BoldItalic.ttf
    name: LiberationSansNarrow
    style: italic
    weight: bold
  - url: liberation/LiberationMono-Regular.ttf
    name: LiberationMono
    style: normal
    weight: normal
  - url: liberation/LiberationMono-Bold.ttf
    name: LiberationMono
    style: normal
    weight: bold
  - url: liberation/LiberationMono-Italic.ttf
    name: LiberationMono
    style: italic
    weight: normal
  - url: liberation/LiberationMono-BoldItalic.ttf
    name: LiberationMono
    style: italic
    weight: bold
```



**docbuilder_page_height** and **docbuilder_page_width**: The page height and width. The defaults can be found in `defaults/main.yml`:
```
docbuilder_page_height: 29.7cm
docbuilder_page_width: 21cm
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
