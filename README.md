HexChat FiSHLiM Reloaded - MOD
==============================

Based on FiSHLiM plugin of BakasuraRCE. I have only modded the plugin_hexchat.h to remove encrypted flag for incoming and outgoing messages. If you want this in your irc-client use the original hexchat-fishlim-reloaded

Installation
------------

### Dependencies

- gio
- openssl
- hexchat
- meson

### Conflicts

You must deactivate the original FiSHLiM version of the HexChat core before using this version

#### User install

```sh
meson builddir -Dlocal_install=true
ninja -C builddir install
```

#### System install

```sh
meson builddir
ninja -C builddir
sudo ninja -C builddir install
```

Features
--------

- Backward compatibility with the database file addon_fishlim.conf from original HexChat module
- CBC mode on SETKEY and KEYX commands
- Store keys in CBC mode (addon_fishlim.conf)
- Detect context in DELKEY command

Usage
-----

- SETKEY command
  - for CBC mode -> /setkey cbc:key
  - for ECB mode -> /setkey ecb:key
  - for ECB mode -> /setkey key
