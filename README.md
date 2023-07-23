# IPSec_Cert
Certificate based ipsec auth

```
apt-get install strongswan libstrongswan-extra-plugins libcharon-extra-plugins -y
openssl req -x509 -nodes -days 3650 -newkey rsa:4096 -keyout /etc/ipsec.d/private/ca-key.pem -out /etc/ipsec.d/certs/ca-cert.pem
openssl req -nodes -newkey rsa:4096 -keyout /etc/ipsec.d/private/serverA-key.pem -out /etc/ipsec.d/certs/serverA-req.pem
openssl x509 -req -in /etc/ipsec.d/certs/serverA-req.pem -CA /etc/ipsec.d/certs/ca-cert.pem -CAkey /etc/ipsec.d/private/ca-key.pem -CAcreateserial -out /etc/ipsec.d/certs/serverA-cert.pem -days 365
```
