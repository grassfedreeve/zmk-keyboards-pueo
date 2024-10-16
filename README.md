# pueo ZMK Module

This repository contains the shield files for the [pueo](https://github.com/grassfedreeve/pueo/) to allow users to build firmware. This can be done by adding the module to the west.yml found in your zmk-config's config directory. There is a full guide available for this here: [ZMK Modules Doc](https://zmk.dev/docs/features/modules)

## Usage

Edit your west.yml file found in your zmk-config's config directory to add the pueo module. Example:

```
manifest:
  remotes:
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: grassfedreeve
      url-base: https://github.com/grassfedreeve
  projects:
    - name: zmk
      remote: zmkfirmware
      revision: main
      import: app/west.yml
    - name: zmk-keyboards-pueo
      remote: grassfedreeve
      revision: main
  self:
    path: config
```
Once you have the module added to your west.yml you can then build firmware as if it was in your config's shield directory or in ZMK main.

## Cofiguration

By default the nice!nano controllers are designed to be face up, however the firmware also supports having the controllers facedown by adding this to your keymap file:
```
/ {
    chosen {
        zmk,kscan = &kscan_facedown;
    };
};
```

# Default Keymap

The default keymap is provided in the module, here is a visual guide made using caksoylar's great [keymap-drawer](https://github.com/caksoylar/keymap-drawer)
![keymap](https://github.com/grassfedreeve/pueo/blob/main/img/example_keymap.svg)
