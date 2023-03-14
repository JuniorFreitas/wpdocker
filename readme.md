crie uma copia do .env.example

cp .env.example .env

--------Configure-----------
MYSQL_ROOT_PASSWORD=
MYSQL_USER=
MYSQL_PASSWORD=

DB_NAME=
DB_USER=
DB_PASSWORD=
----------------------------

no docker-compose modifique os nome dos serviços:
-> site_db
-> site_wordpress
-> site_web

para usar o VHOST utilize:
https://github.com/JuniorFreitas/nginx-multiple-https-websites-on-one-server
configure VHOST com seu dominio e e-mail

- VIRTUAL_HOST=site.meudominio.com
- VIRTUAL_PORT=80
- LETSENCRYPT_HOST=site.meudominio.com
- LETSENCRYPT_EMAIL=admin@meudominio.com

na pasta nginx-conf no arquivo default.conf modifique para o nome do seu serviço
fastcgi_pass site_wordpress:9000;