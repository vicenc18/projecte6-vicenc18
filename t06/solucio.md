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

## 3. Plantillas de usuario
Se crean plantillas para cada departamento.
Cada plantilla pertenece a su grupo y tiene carpeta personal asignada.

- TPL_Gestio → grupo gestio
- TPL_Magatzem → grupo magatzem
- TPL_Gerencia → grupo gerencia

## 4. Usuarios de prueba
Se crean copiando las plantillas de usuario.
Heritan automáticamente grupos y configuración.

- gestio_prova
- magatzem_prova
- gerencia_prova

## 5. Equipo cliente PC1
Se crea una VM con Windows 11, 4 GB de RAM y red NAT.
El equipo se une al dominio y se mueve a la OU Equips.

## 6. Comprobación
Se inicia sesión en PC1 con los tres usuarios de prueba.
Se verifica el acceso y la creación de la carpeta personal.
``