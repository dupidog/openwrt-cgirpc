# cgi-rpc
This is the remote config interface for OpenWrt, via http protocol, transacted by cgi, formatted in json. Please refer to api.txt for more about the api. All parameters can be passed either via GET or POST methods.

To make ipk package, clone this repository to package directory under the openwrt build root or sdk, then type 

```bash
make V=s package/cgi-rpc/compile
```

Api query example:

```bash
QUERY='{"login":"devboard","method":"get","target":"wan"}'
curl -d "rpc=$QUERY" http://192.168.10.1/cgi-bin/cgi-rpc
```
or
```bash
QUERY='{"login":"devboard","method":"get","target":"wan"}'
curl http://192.168.10.1/cgi-bin/cgi-rpc?$QUERY
```
