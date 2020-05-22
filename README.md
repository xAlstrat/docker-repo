
# Registry Docker en Ubuntu

https://www.digitalocean.com/community/tutorials/how-to-set-up-a-private-docker-registry-on-ubuntu-18-04-es

# Instalación

1. Crear/Cambiar auth según tutorial
2. 

    cp .env.example .env
    
3. Añadir dominio del servidor en .env

    
    DOMAIN=my_server_domain.com
    
    
4. Correr docker y nginx

    
    docker-compose up
    
5. Añadir Certificados Let's Script de Cert Bot.

Si ya existen:

    docker-compose exec nginx sed -i "s/localhost/my_server_domain.com/g" /etc/nginx/nginx.conf
    docker-compose exec nginx nginx -s reload
    
Si no (debe estar seteado DOMAIN en .env):

    docker-compose exec nginx letsencrypt-setup

    