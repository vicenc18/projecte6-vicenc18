# T04. Apache vs Nginx

By: Pau Guerrero, Vicenç Obiol i Pau Urrea


## Descripció

Aquest repositori correspoen a la T04 i presenta una pàgina web estàtica orientada a provar la càrrega de recursos externs i el comportament bàsic d'un servidor web.

La pàgina mostra una galeria d'imatges carregades des d'URLs externes i incorpora una petita capa de monitoratge al navegador per visualitzar:

El temps total de càrrega de la pàgina.
L'estat de càrrega de les imatges.
La resposta davant errors de càrrega de recursos.

## Objectiu

L'objectiu principal és disposar d'un recurs senzill per comparar el comportament d'entorns servits amb Apache i Nginx, especialment en aspectes com:

El lliurament de contingut estàtic.
La gestió de múltiples peticions simultànies.
El temps de resposta percebut al client.
La càrrega d'actius externs en paral·lel.

## Fitxers del projecte

index.html: pàgina principal amb l'estructura, els estils i l'script de monitoratge de càrrega.

## Funcionament

Quan s'obre la pàgina al navegador:

1. Es carreguen diverses imatges externes de manera concurrent.
2. El navegador calcula el temps total de càrrega mitjançant la Performance API.
3. Es mostra el nombre d'imatges carregades en temps real.
4. Si alguna imatge falla, es mostra un missatge d'error dins del bloc corresponent.

## Ús

Descarrega l'arxiu index.html a la carpeta /var/www/projectenexus del teu servidor web (Apache o Nginx) i usa l'eina ab per realitzar proves de càrrega.
bash

wget https://github.com/SMX2n/Projecte6-T04/blob/24d6e63ec74c2b061460360ce4471d0d174d1f79/index.html

És important assegurar-se que el servidor que està actiu és el que voleu provar:
bash

sudo systemctl status apache2  # Per Apache
sudo systemctl status nginx    # Per Nginx

Si teniu actiu nginx i voleu usar Apache:
bash

sudo systemctl disable nginx --now
sudo systemctl enable apache2 --now

Pel contrari, si voleu usar Nginx:
bash
sudo systemctl disable apache2 --now
sudo systemctl enable nginx --now

A continuació **cal eliminar a l'arxiu de configuració de virtual host (Apache i Nginx) la redirecció cap la pàgina segura**. Com que el certificat és autosignat, no carregaria la pàgina.

Un cop eliminada la redirecció, recarregeu el servei:

 systemctl reload apache2 o systemctl reload nginx.

Les proves les farem amb la utilitat ab:

Em primer lloc, a Zorin instal·leu les utilitats d'Apache:
bash

sudo apt install apache2-utils -y
bash

ab -n Nombre peticions -c usuaris concurrents URL

Per exemple, per provar un escenari suau i un d'exigent faríem:
bash

ab -n 1000 -c 10 http://www.projectenexus.test/

ab -n 10000 -c 100 http://www.projectenexus.test/

## Resultats

Anoteu els resultats que obteniu igual que a la prova anterior.

Què cal lliurar

Crear una taula comparativa amb les dades obtingudes:

| Mètrica | Apache  prova lleugera | Nginx prova lleugera | Apache prova d’estrès | Nginx prova d’estrès |
| :---- | :---- | :---- | :---- | :---- |
| Time taken for test | 0.204 s | 0.058 s | 1.304 s | 0.488 s |
| Transfer rate | 35067.29 kB/s | 123142.66 kB/s | 54806.66 kB/s | 145987.17 kB/s |
| RPS | 4904.92 #/s | 17292.66 #/s | 7665.90 #/s | 20500.67 #/s |
| Time per request | 2.039 ms | 0.578 ms | 13.045 ms | 4.878 ms |
| Completed request | 1000 | 1000 | 10000 | 10000 |
| Failed request | 0 | 0 | 0 | 0 |



## Tecnologies utilitzades

HTML5
CSS3
JavaScript

## Autor

L'arxiu index.html ha estat generat amb Gemini Canva.
