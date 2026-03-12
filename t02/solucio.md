# t02 instalacio i configuracio de apache i negix
## 1) Instal·lació i configuració base
 
''' bash 
 sudo apt install -y apache2
'''
<<<<<<< HEAD
<<<<<<< HEAD

![](img\1.png)

=======
![scsc](img\t02-1.png)
>>>>>>> 39d8631054713dea6e4fa2f702233f935ed92f3c
=======

<img src="img\t02-1.png" alt="5" width="100" height="auto">
>>>>>>> 3197ceaf44b124e2d7192d032d13b8ab15db8ff4

verificacions

''' bash 

sudo systemctl status apache2

'''
<img src="img\t02-2.png" alt="5" width="100" height="auto">

### 1.2. Usuari i permisos de publicació
 Resultats mostrant www-data i permisos de /var/www.

 ![](img\t02-3.png)

 ## 2) VirtualHosts (multidomini)
 ### 2.1. Estructura de directoris

 sudo mkdir -p /var/www/projectenexus18.test/public_html/errors
 sudo mkdir -p /var/www/academia18.test/public_html/errors

 ![](img\t02-4.png)

 ### 2.2. Simular DNS amb /etc/hosts
sudo nano /etc/host

Afegeix:

127.0.0.1   projectenexus18.test
127.0.0.1   academia18.test

![](img\t02-5.png)

### 2.3. VirtualHosts HTTP (:80) amb redirecció a HTTPS

/etc/apache2/sites-available/projectenexus18.test.conf

![](img\t02-6.png)

 /etc/apache2/sites-available/academia18.test.conf

 ![](img\t02-7.png)

 Activacio:

 ![](img\t02-8.png)

 ## 3) Error 404 personalitzat (mínim un lloc)

 /var/www/projectenexus.test/public_html/errors/404.html:
 Afegir al vhost (HTTP o millor HTTPS):

![](img\t02-9.png)

## 4) Seguretat i certificats (HTTPS)
### 4.1. Habilitar SSL i capçaleres


sudo a2enmod ssl headers
sudo systemctl reload apache2

![](img\t02-10.png)
