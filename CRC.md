## Deploy console on CRC

Required:
```
$ crc config view
- consent-telemetry                     : no
- cpus                                  : 7
- host-network-access                   : true
- memory                                : 12228
- network-mode                          : user
```

Start the cluster:
```
$ crc start
```

Podman login:
```
$ podman login -u='gfournie+test_repository' -p='<xxxxxxx>' quay.io
```

Project:
```
$ make images
$ make push
$ make deploy-plugin
```

Check logs:
```
oc project plugin-camel-openshift-console-plugin
$ stern camel-openshift-console-plugin
```

Log in:
```
https://console-openshift-console.apps-crc.testing
```

For login infos: 
```
crc console --credentials
```

## Deploy workload on CRC

### Camel jbang kubernetes plugin

