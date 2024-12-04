# Bootcamp DevOps Engineer by EducacionIT 2024~2025
### realizado por Hernán Fernández Brando

## Desafío#02
### Objetivo
Este desafío tiene como objetivo realizar la configuración de un webhook en un repositorio de Github y también crear un simple pipeline para ejecutar un build y testear un proyecto NodeJS.

### Escenario
Nuestra organización nos encomendó la tarea de realizar una prueba de concepto para crear un CI/CD de nodejs, necesitan entender cómo se debe realizar el proceso de build para una API hecha en nodejs.
Por este motivo, nos entregaron una aplicación de ejemplo hecha en esta tecnología, este proyecto cuenta con una prueba integrada hecha en la herramienta Jest propia de este framework de desarrollo.
El referente de desarrollo, nos encargó realizar la configuración de un webhook que permita hacer un build automático cada vez que se produzca un push o un pull request, esto puede ayudar para automatizar la ejecución del job para este CI/CD.

### Requisitos
1. Crear un fork del siguiente proyecto en nuestro cuenta de Github: [nodejs-helloworld-api](https://github.com/edgaregonzalez/nodejs-helloworld-api)

2. Realizar la configuración del github webhook para inicializar el job cada vez que se produce un push o un se crea un PR.
2. Exponer mediante ngrok el servicio de Jenkins para que este pueda ser accedido por Github.
2. Elaborar un jenkins pipeline para que ejecute los pasos para desarrollo, tomar las instrucciones del README.md del proyecto.

### Documentación de referencia

| Titulo | Descripción | URL |
| ---- | ---- | ---- |
| Ngrok developer ingress | Permite exponer un servicio local hacia internet. | https://ngrok.com/ | 
| Github Webhooks | Documentación oficial sobre los webhook. | https://docs.github.com/en/webhooks/about-webhooks |
| Jenkins Github plugin | Plugin utilizado para integrar los webhook de github a Jenkins.| https://plugins.jenkins.io/github/ | 
| Instalar nvm para nodejs | Guia como instalar nvm en un sistema linux, nvm permite correr distintas versiones de nodejs en nuestro entorno local. | https://nodejs.org/en/download/package-manager/ |

### Entregables

Los entregables establecidos para este proyecto con:
1. Código fuente del pipeline de Jenkins publicado en un repositorio de Github (El repositorio debe ser público).
2. Guía detallada de cómo utilizar el job de Jenkins en un archivo formato DOC o PDF (Adicional al documento y como algo opcional puede crear un archivo README.MD como parte del repositorio).
3. El documento debe contener un apartado de evidencia de las pruebas con resultado exitoso.

#### Entregable 0. Preparación del entorno

Previo a la ejecución de los pipeline fue necesario realizar las siguientes acciones:
##### Instalar ngrok
Instalado en clase, incluso se habilitó la url fija disponible para las cuentas gratuitas.
La salida por linea de comandos, obtenida al disponibilizar en internet el recurso de la máquina multipass con jenkins instalado, es la siguiente:
```bash
ngrok
(Ctrl+C to quit)

Sign up to try new private endpoints https://ngrok.com/new-features-update?ref=private

Session Status                online
Account                       hfbrando (Plan: Free)
Update                        update available (version 3.18.4, Ctrl-U to update)
Version                       3.18.1
Region                        South America (sa)
Web Interface                 http://127.0.0.1:4040
Forwarding                    https://super-refined-gelding.ngrok-free.app -> http://localhost:8080
Connections                   ttl     opn     rt1     rt5     p50     p90
                              0       0       0.00    0.00    0.00    0.00  
```
##### Instalar plugin `nvm` para `nodejs`
Para realizar esto se 


#### Entregable 1. Códigos Fuente Jenkins

```groovy
post {
    success {
        echo "Usuario: ${params.login}"
        echo "Password: ${password}"
        echo "Departamento: ${params.department}"
    }
    aborted {
        echo "El usuario no fue creado"
        sh "sudo userdel -r ${params.login}"
    }
    failure {
        echo "No se pudo crear el provisionamiento y el usuario fue eliminado"
        sh "sudo userdel -r ${params.login}"
    }
}
```

#### Entregable 2. Guía de cómo utilizar el job

##### Readme Creación de Usuarios


#### Entregable 3. Evidencia de las pruebas con resultado exitoso

##### Creación de Usuarios

