openwrt-uci
===========

Setting of uci config values on openwrt systems. This library module can be easily used by playbooks and roles.

Official UCI documentation: [http://wiki.openwrt.org/doc/uci] and [http://wiki.openwrt.org/doc/techref/uci]

Requirements
------------

* lua interpreter

Usage in roles or playbooks
---------------------------

Set a value:
```
uci:
  command: set
  config: "{{config}}"
  section: "{{section}}"
  type: "{{type}}"
  index: "{{index}}"
  option: "{{option}}"
  value: "{{value}}"
```

Set values as object:
```
uci:
  command: set_object
  config: "{{config}}"
  section: "{{section}}"
  type: "{{type}}"
  index: "{{index}}"
  option: "{{option}}"
  values:
    key: "{{value}}"
    another_key: "{{another_value}}"
```

Delete a value:
```
uci:
  command: delete
  config: "{{config}}"
  section: "{{section}}"
  index: "{{index}}"
  option: "{{option}}"
```

Commit:
```
uci:
  command: commit
  config: "{{config}}"
```

Options
-------

| parameter | required | type    | choices                                                                                          | comments                                                                                                           |
|-----------|----------|---------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
| command   | yes      | string  | <ul><li>get</li><li>set</li><li>delete</li><li>commit</li><li>get_all</li></ul>                  | Specifies the UCI command                                                                                          |
| config    | yes      | string  |                                                                                                  | Specifies the UCI config. Mandatory for all commands                                                               |
| section   | no       | string  |                                                                                                  | Specifies the UCI section name. Mandatory if no index is set.                                                      |
| type      | no       | string  |                                                                                                  | Specifies the UCI section type. Mandatory if a section will be created.                                            |
| index     | no       | number  |                                                                                                  | Specifies the index for the item within a section-array. Mandatory if you changing values within section-arrays.   |
| option    | no       | string  |                                                                                                  | Specifies the UCI option name within sections. Mandatory for commands set, set_object and delete.                  |
| value     | no       | string  |                                                                                                  | Specifies the value to set as section option. Mandatory for command 'set'.                                         |
| values    | no       | string  |                                                                                                  | Specifies the value to set as section option. Mandatory for command 'set_object'.                                  |

See for UCI documentation:
* [OpenWRT Wiki / The UCI System](http://wiki.openwrt.org/doc/uci)
* [OpenWRT Wiki / UCI (Unified Configuration Interface) – Technical Reference](http://wiki.openwrt.org/doc/techref/uci)

Got idea from:
* [lefant/ansible-openwrt](https://github.com/lefant/ansible-openwrt)
* [lefant/ansible-openwrt-uci](https://github.com/lefant/ansible-openwrt-uci)
