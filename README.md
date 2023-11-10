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

## Test swiftest-cli with https
```shell
./swiftest-cli -k --mbps -s https://<speedtest-server-ip> -p 3 --etsi --etsi-download-mb 200 --etsi-upload-mb 200 -t 30
```

## Test swiftest-cli with http
```shell
./swiftest-cli -k --mbps -s http://<speedtest-server-ip>:8008 -p 3 --etsi --etsi-download-mb 200 --etsi-upload-mb 200 -t 30
```
