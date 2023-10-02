# AREP06 : TALLER DE TRABAJO INDIVIDUAL EN PATRONES ARQUITECTURALES

Proyecto para profundizar conocimientos sobre AWS y Docker.

### Prerequisitos

Para elaborar este proyecto se requirio de : 


Maven: Apache Maven es una herramienta que maneja el ciclo de vida del programa.



Git: Es un sistema de control de versiones distribuido (VCS).



Java 17: Java es un lenguaje de programación de propósito general orientado a objetos, portátil y muy versátil.


Docker : Automatiza el despliegue de aplicaciones dentro de contenedores de software, proporcionando una capa adicional de abstracción y automatización de virtualización de aplicaciones en múltiples sistemas operativos.

AWS : Es una colección de servicios de computación en la nube pública que en conjunto forman una plataforma de computación en la nube, ofrecidas a través de Internet por Amazon.com

### Instalación

Clonamos el repositorio

```
    git clone 

```
Se accede a la carpeta principal del repositorio repositorio que acabamos de clonar

	 cd AREP06

Hacemos la construccion del proyecto

	 mvn package
---
### Corriendo
Corremos los siguientes comando
	
	 mvn clean package install
	 mvn clean install


Ahora debemos clonar el otro repositorio donde tendremos el round robin

[![Repo donde esta Round robin](https://github.com/julianCS21/AREPRoundBound)]

Y hacemos los mismos pasos

```
    cd AREPRoundBound
    mvn package
    mvn clean package install
    mvn clean install 

```
Una vez tengamos los dos proyectos bien compilados y listos para ejecutar, construimos sus imagenes respectivamente

```
    docker build --tag logservices .
    docker build --tag roundrobin-java .
```

tambien cabe recordar que debe bajar la imagen de mongo


```
    docker pull mongo
```
una vez tenga todo lo anterior hecho, asegurate estar en el directorio raiz de este repositorio y ejecuta el siguiente comando.


```
    docker-compose up -d  
```

con esto nos dirigimos al http://localhost:8080/app.html y nos carga algo asi:

![image](https://github.com/julianCS21/AREP06/assets/96396177/2b433643-b86d-4479-b85f-aee82c210812)


---
### Corriendo test

Ejecutamos el comando

	mvn test
	
---


### Arquitectura del programa.


![image](https://github.com/julianCS21/AREP06/assets/96396177/4887a165-897e-4a90-9462-d0b8a21b2f86)

Esta arquitectura se basa en tres componentes realmente:


## Round Robin


Contenedor que actua como frontend del proyecto, su objetivo es implementar el algoritmo de Round Robin para distribuir la carga entre el backend del proyecto 



## LogService

Contenedor encargado del backend, el cual lee un mensaje y lo guarda en la base de datos, luego retorna los ultimos 10 mensajes.

Este contenedor cuenta con 3 instancias para otorgar mayor disponibilidad al proyecto.


## mongoDB

Base de datos de mongo.


## Video prueba del despliegue 

[![Video](https://www.youtube.com/watch?v=kVhG_CmOYck&ab_channel=JulianCastillo)]

El video demuestra que esta desplegado en la nube de AWS, ademas a traves de los logs de el contenedor de Round Robin se puede observar el funcionamiento del algoritmo.



## Construido con

* [Maven](https://maven.apache.org/): Apache Maven es una herramienta que estandariza la configuración del ciclo de vida del proyecto.
* [Git](https://rometools.github.io/rome/):  Es un sistema de control de versiones distribuido (VCS).
* [Intellj](https://www.jetbrains.com/es-es/idea/): IntelliJ IDEA es un IDE que ayuda a los desarrolladores a escribir, depurar y administrar código de manera más eficiente y efectiva, con muchas características que facilitan el proceso de desarrollo de software.
* [Java 17](https://www.java.com/es/): Lenguaje de programación de propósito general con enfoque a el paradigma de orientado a objetos, y con un fuerte tipado de variables.
* [Html](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/HTML_basics): es un lenguaje de marcado que estructura una página web y su contenido.
* [JavaScript](https://developer.mozilla.org/es/docs/Learn/JavaScript/First_steps/What_is_JavaScript): lenguaje de programación que los desarrolladores utilizan para hacer paginas web dinamicas.
* [CSS](https://developer.mozilla.org/es/docs/Web/CSS) Lenguaje para darles estilos a paginas web.
* [Docker](https://www.docker.com) Automatiza el despliegue de aplicaciones dentro de contenedores de software.
* [AWS](https://aws.amazon.com/es/free/?trk=8fa18207-f2c2-4587-81a1-f2a3648571b3&sc_channel=ps&ef_id=CjwKCAjwseSoBhBXEiwA9iZtxmEwAgfk7jPE4NlzdkF60BOim6V2loEW5eNT7e8yJcbyO0g8dZpJaBoCRIEQAvD_BwE:G:s&s_kwcid=AL!4422!3!647999789205!e!!g!!aws!19685287144!146461596896&gclid=CjwKCAjwseSoBhBXEiwA9iZtxmEwAgfk7jPE4NlzdkF60BOim6V2loEW5eNT7e8yJcbyO0g8dZpJaBoCRIEQAvD_BwE&all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Types=*all&awsf.Free%20Tier%20Categories=*all) colección de servicios de computación en la nube pública que en conjunto forman una plataforma de computación en la nube


## Autor
* **[Julián David Castillo Soto](https://www.linkedin.com/in/julián-david-castillo-soto-118856216/)**  - [julianCS21](https://github.com/julianCS21)

## Licencia
**©** Julián David Castillo Soto, Estudiante de Ingeniería de Sistemas de la Universidad Escuela Colombiana de Ingeniería Julio Garavito.
