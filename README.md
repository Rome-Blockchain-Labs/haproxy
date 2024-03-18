# haproxycfg
- fullnode: rpc.romenet.io/<network>
- archive: data.romenet.io/<network>

## Networks
- Avalanche
- Evmos
- Flare
- Kava


## Test letsencrypt
sometimes letsencrypt cerbot bugs and fails giving certs and only
way is to trigger couple webserver test to untrigger it??
```
# preq
echo "Hello, this is a test." > .well-known/acme-challenge/testfile
# this server
python3 -m http.server 8888
# at local pc
curl http://data.romenet.io/.well-known/acme-challenge/testfile
```

## Linting / Checking configs
```sh
haproxy -c -f /etc/haproxy/haproxy.cfg
```

## Monitoring
Can use hatop or prometheus exporter.
```sh
hatop -s /var/run/haproxy.sock
```
