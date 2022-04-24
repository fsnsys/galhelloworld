# galhelloworld
Proyecto Challenge DevOps - Bco Galicia

Imagen usada: httpd-2.4 - Apache 2.4
Código/template usado: HTML Básico Hello World + Imagen galicia

Jenkinsfile - CD Pipeline
Contempla los Stages:

1 - Acceso a Github. Acceso a repo y descarga del código

2 - B&D (Build & Deploy). Realiza compilado del código y posteriormente genera un Deploy nuevo en el namespace, dando lugar al nuevo versionado del pod con el código recién descargado y aplicado.
