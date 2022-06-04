# ans_role_config_i3wm_wm

Install and configure the i3wm window manager.

[![Release](https://img.shields.io/github/release/digimokan/ans_role_config_i3wm_wm.svg?label=release)](https://github.com/digimokan/ans_role_config_i3wm_wm/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.md "Project License")

## Table Of Contents

* [Supported Operating Systems](#supported-operating-systems)
* [Requirements](#requirements)
* [Quick Start](#quick-start)
    * [Use From Playbook](#use-from-playbook)
* [Role Options](#role-options)
* [Contributing](#contributing)

## Supported Operating Systems

* Ubuntu focal (20.04), hirsute (21.04), impish (21.10)
* Arch Linux.
* FreeBSD.

## Requirements

* [Xorg Server Components](https://www.x.org/wiki/) and [Xorg User Scripts](https://venam.nixers.net/blog/unix/2020/01/27/xconfig.html).
    * [digimokan/ans_role_config_xorg](https://github.com/digimokan/ans_role_config_xorg) may be used.
* [fonts](../defaults/main/wm_components/fonts.yml).
* [terminal emulator](../defaults/main/wm_components/terminal.yml).
* [compositor](../defaults/main/wm_components/compositor.yml) (optional).
* [background image display utility](../defaults/main/wm_components/bg_wallpaper.yml) (optional).
* [screen brightness utility](../defaults/main/wm_components/multimedia.yml) (optional).

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

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_i3wm_wm/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

