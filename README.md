# Fast nginx reverse proxy with HTTPS and Basic Auth enabled

The repository shows a fast and easy to use nginx reverse proxy with enabled basic authentication and https (with self-signed certificate)

## How to use:
1. Create you certificate:
```
openssl genrsa -out test.local.key 2048
openssl req -new -x509 -key test.local.key -out test.local.cert -days 3650 -subj /CN=test.local
```
put them in `./cert` dir

2. Add your application as `web` in `docker-compose.yml`

3. Configure path to your keys in `nginx.conf`

4. Add your Basic-auth users into `.htpasswd`
The default is `foo:bar`

5. Start:
```
docker-compose up -d
```
