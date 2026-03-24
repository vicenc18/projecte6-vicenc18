# GUIA / MEMÒRIA TÈCNICA — Migració d’Apache a Nginx

## 1 Preparació de l’entorn 
### 1.1 Aturada i deshabilitació d’Apache 

systemctl stop apache2
systemctl disable apache2

(captures de pantalla)

### 1.2 Instal·lació de Nginx

apt update
apt install nginx -y

(captures de pantalla)

### Carpeta web (creació i permisos) 

mkdir -p /var/www/projectenexus18.test
mkdir -p /var/www/academia18.test
chown -R www-data:www-data /var/www/

(captures de pantalla)

## 2 Configuració de Server Blocks 

### 2.1
Ruta: /etc/nginx/sites-available/projectenexus18.conf

captura

### 2.2 Fitxer de configuració academia.conf 
 Ruta: /etc/nginx/sites-available/academia18.conf

 captura

### 2.3 Activació de configuracions

ln -s /etc/nginx/sites-available/projectenexus.conf /etc/nginx/sites-enabled/

ln -s /etc/nginx/sites-available/academia.conf /etc/nginx/sites-enabled/

captura

### 2.4. Verificació

nginx -t 

captura