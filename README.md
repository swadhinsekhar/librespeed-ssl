# Librespeed Server

## Add system IP Address
IP.<next-highest-num> <ip-address>

Example:
`IP.2 = 192.168.10.100`
`IP.3 = 192.168.20.100`

```shell
vi san.cnf
```

## Generate Certs
```shell
openssl req -x509 -nodes -days 1000 -newkey rsa:2048 -keyout ssl/key.pem -out ssl/cert.pem -config san.cnf
```

## Verify Certs
```shell
openssl x509 -in ssl/cert.pem -text -noout
```

## docker-compose build commands
```shell
sudo docker-compose up --build -d
```

## docker-compose down commands
```shell
sudo docker-compose down
```

## docker-compose logs
```shell
sudo docker-compose logs -f
```

## Test with https
```shell
./<speedtest-agent> -s https://<speedtest-server-ip>
```

## Test with http
```shell
./<speedtest-gent> -s http://<speedtest-server-ip>:8008
```
