openwrt-uci
===========

setting of uci config keys on openwrt systems. this is just the
library module so that other openwrt roles can dependend on it.

compare: [http://wiki.openwrt.org/doc/uci] and [http://wiki.openwrt.org/doc/techref/uci]

Requirements
------------

* lua

Usage
-----

Set a value:
```
uci: command=set config={{config}} section={{section}} type={{type}} index={{index}} option={{option}} value={{value}}
```

Set values as list:
```
uci: command=set_list config={{config}} section={{section}} type={{type}} index={{index}} option={{option}} value={{values|comma separated}}
```

Delete a value:
```
uci: command=delete config={{config}} section={{section}} type={{type}} index={{index}} option={{option}}
```

Commit:
```
uci: command=commit config={{config}}
```

Options
-------

| parameter | required | default | choices                                                                                          | comments                                                                                                           |
|-----------|----------|---------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
| command   | yes      |         | <ul><li>get</li><li>set</li><li>set_list</li><li>delete</li><li>commit</li><li>get_all</li></ul> | Specifies the UCI command                                                                                          |
| config    | yes      |         |                                                                                                  | Specifies the UCI config. Mandatory for all commands                                                               |
| section   | no       |         |                                                                                                  | Specifies the UCI section name. Mandatory of you want to change an option within simple elements.                  |
| type      | no       |         |                                                                                                  | Specifies the UCI section type. Mandatory if you want to change options within array-like elements.                |
| index     | no       |         |                                                                                                  | Specifies the index of the array-like element. Mandatory if you want to change options within array-like elements. |
| option    | no       |         |                                                                                                  | Specifies the UCI option name within sections. Mandatory to set or delete options.                                 |
| value     | no       |         |                                                                                                  | Specifies the value to set as section option. Mandatory when using command 'set'.                                  |

See for UCI documentation:
[http://wiki.openwrt.org/doc/uci]: http://wiki.openwrt.org/doc/uci
[http://wiki.openwrt.org/doc/techref/uci]: http://wiki.openwrt.org/doc/techref/uci

Further information:
[https://github.com/lefant/ansible-openwrt]: https://github.com/lefant/ansible-openwrt
