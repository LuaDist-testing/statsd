Lua Statsd client
=================

`lua-statsd-client` is a [Statsd](https://github.com/etsy/statsd) client for
Lua. It supports all Statsd meter types.

Installation
------------

```sh
% luarocks install statsd
```

Usage
-----

```lua
local statsd = require "statsd"

statsd.host = "stats.mysite.com" -- default: 127.0.0.1
statsd.port = 8888 -- default: 8125
statsd.namespace = "mysite.stats" -- default: none

statsd.gauge( "users", #my_users_table )
statsd.counter( "events", 5 )
statsd.increment( "events", 1 )
statsd.decrement( "events", 3 )
statsd.timer( "page_render", 105 )
statsd.histogram( "page_render_time", 105 )
statsd.meter( "page_load", 1 )
```

Development
-----------

```
% luarocks install busted
% busted statsd_test.lua
```

