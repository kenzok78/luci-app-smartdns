# luci-app-smartdns

## Package Description

LuCI support for SmartDNS. SmartDNS is a local high-performance DNS server that supports finding fastest IP, ad filtering, and avoiding DNS poisoning.

## Features

- Local DNS server with speed optimization
- Upstream DNS server configuration (UDP, TCP, TLS, HTTPS)
- Second DNS server for fallback
- DNS64 server support
- Proxy server support for upstream queries
- Domain-based forwarding and blocking
- IP-based rules and blacklists
- Cache with persistence
- Certificate-based DNS (DoT, DoH)
- DNSCrypt support
- Auto-update domain lists

## Dependencies

- `smartdns`
- `luci-compat`

## Normalized Package Path

This is a normalized and fixed version of the original `kenzok8/openwrt-packages` package, following standard OpenWrt LuCI app layout.

## Bugs Fixed

- Controller: `nixio.fs.access` called without local `require "nixio.fs"` (missing `local fs` declaration)
- Controller: `luci.sys.call` and `luci.http` used without local requires
- Controller: global variable leaks (`e`, `ipv6_server`, `str`)
- Model: duplicate `require("nixio.fs")` call removed
- Model: unused `require("luci.http")` and `require("luci.dispatcher")` removed
- Model: `return m` referencing undefined `m` variable removed
- Model: unused `local uci` variable kept for `get_config_option` function
- CBI model: duplicate `require("nixio.fs")` call removed
- CBI model: unused `require("luci.http")` and `require("luci.dispatcher")` removed
- upstream.lua: syntax error on line 19 (`%{` replaced with `string.format`)
- uci-defaults script: missing `IPKG_INSTROOT` check added
- po/zh-cn directory renamed to po/zh_Hans

## Original Author

Nick Peng (Ruilin Peng) &lt;pymumu@gmail.com&gt;
