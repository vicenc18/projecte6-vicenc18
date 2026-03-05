# t07 TransLògic: Administració Avançada i Seguretat Corporativa
 ## 1.1. Política Global (Default Domain Policy)
 Passos:
Obre Group Policy Management.

Ves a: Domains → translogic.local → Default Domain Policy.

Clic dret → Edit.
Navega a:
Computer Configuration →
Policies →
Windows Settings →
Security Settings →
Account Policies →
Password Policy

![](IMG\1-T07.png)

![](IMG\2-T07.png)

![](IMG\3-T07.png)

## 1.2. Política per al grup Gerencia

Objectiu:

Contrasenya mínima: 18 caràcters
Caducitat: 28 dies
Sense complexitat

Passos:

A Group Policy Management: clic dret a l’OU Gerencia → Create a GPO…
Nom: GPO_Password_Gerencia.
Edit.
Navega a la mateixa ruta que abans.

Configura:

Minimum password length = 18
Maximum password age = 28 days
Password must meet complexity requirements = Disabled

![](IMG\4-T07.png)

![](IMG\5-T07.png)

![](IMG\6-T07.png)

![](IMG\7-T07.png)


