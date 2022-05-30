# ans_role_config_i3wm_wm

Install and configure the i3wm window manager.

[![Release](https://img.shields.io/github/release/digimokan/ans_role_config_i3wm_wm.svg?label=release)](https://github.com/digimokan/ans_role_config_i3wm_wm/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.md "Project License")

## Table Of Contents

* [Purpose](#purpose)
* [Supported Operating Systems](#supported-operating-systems)
* [Requirements](#requirements)
* [Quick Start](#quick-start)
    * [Use From Playbook](#use-from-playbook)
* [Role Options](#role-options)
* [Role Dependencies](#role-dependencies)
* [Contributing](#contributing)

## Purpose

* Install Xorg components and [i3wm](https://i3wm.org/).
* Install various supporting desktop environment add-on utilities.
* Configure i3wm and supporting utilities.

## Supported Operating Systems

* Ubuntu focal (20.04), hirsute (21.04), impish (21.10)
* Arch Linux.
* FreeBSD.

## Requirements

### Must Be Installed And Configured Separate From This Role

* All core Xorg server components.
* System and user `.Xresources`, `.Xmodmap`, `.xinitrc.d/` scripts, and
  `.xprofile` are configured to be read on Xorg start.
* An optional compositor (`compton`, `picom`, etc) - see
  [defaults](../defaults/main/wm_components/compositor.yml).
* Fonts specified in [defaults](../defaults/main/wm_components/fonts.yml).

### Installed Automatically By This Role

* [i3lock](https://github.com/i3/i3lock), to use as the i3 screen locker.
* [feh](https://github.com/derf/feh), for displaying a background image.

## Quick Start

### Use From Playbook

1. Create `requirements.yml` in ansible project root, and add this content:

   ```yaml
   # requirements.yml
   - src: https://github.com/digimokan/ans_role_config_i3wm_wm
   ```

2. From the project root directory, install/download the role:

   ```shell
   $ ansible-galaxy install --role-file requirements.yml --roles-path ./roles --force-with-deps
   ```

   * _NOTE:_ `--force-with-deps` _ensures subsequent calls download updates_

3. Include the role like any local role, from the project playbook:

   ```yaml
   # playbook.yml
   - hosts: localhost
     connection: local
     tasks:
       - name: "Configure the i3wm window manager"
         ansible.builtin.include_role:
           name: ans_role_config_i3wm_wm
         vars:
           user_name: "user2"
   ```

## Role Options

See the role `defaults` files for main role vars listings:

  * [defaults](../defaults/main/)

Define these _required_ vars for the role:

  * `user_name`: name of primary i3wm user to configure the desktop for

## Role Dependencies

* [ans_role_config_xorg](https://github.com/digimokan/ans_role_config_xorg)

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_i3wm_wm/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

