# Installation

CarbonVPN is built using autotools, you will need `automake` and `autoconf` installed on your system.

Download a copy of the source by cloning the [repository](https://github.com/yorickdewid/CarbonVPN) or download a release.

**Note:** At the time of writing CarbonVPN is still in development, this means there are no releases at the moment.

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

## Run

You can run the client or server by simply calling the binary `./carbond [OPTIONS] [COMMANDS]`.