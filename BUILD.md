### create server certs
```shell
openssl genrsa > privkey.pem
openssl req -new -x509 -key privkey.pem > fullchain.pem
```

### install app 
```shell
# resolve npm install error - Invalid tag name ">=^16.0.0" #661
npm install --legacy-peer-deps
```

### config MEDIASOUP_LISTEN_IP for resolve sdp ice candidate ip error
```json
    "start": "DEBUG=${DEBUG:='*mediasoup* *INFO* *WARN* *ERROR*'} INTERACTIVE=${INTERACTIVE:='false'} MEDIASOUP_LISTEN_IP=127.0.0.1 node server.js",
```