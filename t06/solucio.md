# Guía de despliegue del dominio

## 1. Estructura de Unidades Organizativas (OU)
Se crean OU para separar usuarios, grupos y equipos.
Esto facilita la administración, las GPO y el crecimiento del dominio.

- Usuaris
  - Gestio
  - Magatzem
  - Gerencia
- Grups
- Equips


![](IMG\t06-01.png)

## 2. Creación de grupos
Se crean los grupos de seguridad: gestio, magatzem y gerencia.
El grupo personal incluye a todos los grupos anteriores.

![](IMG\t06-02.png)



## 3. Plantillas de usuario
Se crean plantillas para cada departamento.
Cada plantilla pertenece a su grupo y tiene carpeta personal asignada.

- TPL_Gestio → grupo gestio
- TPL_Magatzem → grupo magatzem
- TPL_Gerencia → grupo gerencia

![](IMG\t06-05.png)

![](IMG\t06-07.png)

![](IMG\t06-4.png)


## 4. Usuarios de prueba
Se crean copiando las plantillas de usuario.
Heritan automáticamente grupos y configuración.

- gestio_prova
- magatzem_prova
- gerencia_prova

![](IMG\t06-08.png)


## 5. Equipo cliente PC1
Se crea una VM con Windows 11, 4 GB de RAM y red NAT.
El equipo se une al dominio y se mueve a la OU Equips.

![](IMG\t06-14.png)


## 6. Comprobación
Se inicia sesión en PC1 con los tres usuarios de prueba.
Se verifica el acceso y la creación de la carpeta personal.
``

![](IMG\t06-10.png)

![](IMG\t06-12.png)

![](IMG\t06-09.png)


