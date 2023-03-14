Crie uma copia do .env.example

```shell
cp .env.example .env
```

**Configure as credenciais**
```env
MYSQL_ROOT_PASSWORD=
MYSQL_USER=
MYSQL_PASSWORD=

DB_NAME=
DB_USER=
DB_PASSWORD=
```
No docker-compose modifique os nome dos serviços:

```yml
-> site_db
-> site_wordpress
-> site_web
```
Para usar o VHOST utilize:
[https://github.com/JuniorFreitas/nginx-multiple-https-websites-on-one-server](https://github.com/JuniorFreitas/nginx-multiple-https-websites-on-one-server)
configure VHOST com seu dominio e e-mail

```yml
- VIRTUAL_HOST=site.meudominio.com
- VIRTUAL_PORT=80
- LETSENCRYPT_HOST=site.meudominio.com
- LETSENCRYPT_EMAIL=admin@meudominio.com
```

na pasta nginx-conf no arquivo default.conf modifique para o nome do seu serviço
fastcgi_pass site_wordpress:9000;

```shell
docker-compose up -d
```
