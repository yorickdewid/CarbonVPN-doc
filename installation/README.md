# Installation

CarbonVPN is built using autotools and you will need to have `automake` and `autoconf` installed on your system.

Download a copy of the source by cloning the [repository](https://github.com/yorickdewid/CarbonVPN) or download a release.

**Note:** At the moment of writing CarbonVPN is still in development and there are no releases yet.

## Dependencies

CarbonVPN depends on two libraries:
* `libev` available as `libev-dev` or `libev-devel`
* `libsodium` available [here](https://github.com/jedisct1/libsodium)

## Building

This follows the usual ritual:

```
./autogen.sh
./configure
make
```

Now you can (as root) install CarbonVPN with `make install`