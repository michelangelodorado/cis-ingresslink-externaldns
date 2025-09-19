1. use the yaml files

2.
openssl req -x509 -newkey rsa:2048 -nodes -days 365 \
  -keyout nginx-web.key -out nginx-web.crt \
  -subj "/CN=nginx-web.example.com"

3.
kubectl create secret tls nginx-web-secret -n default \
  --cert=nginx-web.crt --key=nginx-web.key
