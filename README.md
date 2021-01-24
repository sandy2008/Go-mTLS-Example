# Go mTLS Example

## How to Run

### Generate Cert Files
```
openssl req -newkey rsa:2048 \
  -new -nodes -x509 \
  -days 3650 \
  -out cert.pem \
  -keyout key.pem \
  -subj "/C=US/ST=California/L=Mountain View/O=Your Organization/OU=Your Unit/CN=localhost"
```

### Server
```
cd server
go run server.go
```

### Client
```
cd client
GODEBUG=x509ignoreCN=0 go run client.go
```