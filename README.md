# certbot-proxy

This docker image is intended for use in conjunction with the `datameta/nginx-ssl-proxy` image.

Example compose usage:

```yaml
certbot:
  image: "datameta/certbot-proxy:v1.0.0"
  volumes:
    - etc-le:/etc/letsencrypt      # Persistent volume for certificates
    - www-certbot:/var/www/certbot # Temporary volume for challenge data
  environment:
    CERTBOT_ARGS: --agree-tos -m {email_address} -d {domain_name} # Fill the blanks
```
