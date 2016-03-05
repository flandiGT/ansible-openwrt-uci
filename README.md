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
uci: command=set config={{config}} section={{section}} option={{option}} value={{value}}
```

Commit
------

```
uci: command=commit config={{config}}
```

Supported commands in future:
-----------------------------

* get
* get_all

See for UCI documentation:
[http://wiki.openwrt.org/doc/uci]: http://wiki.openwrt.org/doc/uci
[http://wiki.openwrt.org/doc/techref/uci]: http://wiki.openwrt.org/doc/techref/uci

Further information:
[https://github.com/lefant/ansible-openwrt]: https://github.com/lefant/ansible-openwrt