# GUIA EXAMEN FUGA
## 1 AFEGIR UN DOMINI AL SERVIDOR (SEXO)

### 2.4 Intalacio del Rol Domine service
Lo primer que ferem es entrar a la part de Manager, I entrar hon diu add Roles and features

![](img/t04v15.png)

Segint d'l apartatde installation Type

![](img/t04v16.png)

Next..

![](img/t04v17.png)

Permet Insta-lar roles de forma centrelitzada als diferents servidors del domini. 

Next...

![](img/t04v19.png)

Next...

![](img/t04v20.png)

Confirmation...

![](img/t04v21.png)

INSTALL..

![](IMG/T04V22.png)

## 2.5 Promoció a domain controller

![](img/t04v23.png)

Entrem on diu Promote this server to a domain controller

![](img/t04v24.png)

I selecionem el tipus de instalacio que volem fer,
Ens pregunta si volem afegir a undomini que ja existeix,

![](img/t0425.png)

Next...

El nivell funcional de bosc i domini 

![](img/P@ssword.png)

next...

Com utilitza DNS i no detecta cap operatiu que contingui el domini triat, ens avisa i procedirà a instal·lar aquest rol al DC. Cliquem directament a Next

![](img/t04v26.png)

next...

Per compatibilitat amb sistemes que encara usen NetBIOS (Samba3, XP en grup de treball...) assigna automàticament un nom NetBIOS al domini.

![](img/t04v27.png)

next....

![](img/t04v28.png)

next..

Ens mostra un resum de les configuracions triades i dóna l’opció de crear un script PowerShell amb elles. Això és molt útil per replicar configuracions.

![](img/T04V29.png)

![](img/t04v30.png)

Instala..

![](img/t04v32.png)

## POSAR UN EQUIP EN DOMINI
### Configurar el DNS del cliente

Abre Configuración → Red e Internet
En Ethernet o WiFi → Editar configuración del adaptador
Haz clic derecho → Propiedades
Selecciona Protocolo de Internet versión 4 (TCP/IPv4)
En DNS, coloca:

Servidor DNS preferido: IP del servidor (ej. 192.168.1.10)

