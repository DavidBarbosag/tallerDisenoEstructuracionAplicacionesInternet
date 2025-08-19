# Taller diseño y estructuración de aplicaciones distribuidas en internet

Servidor HTTP mínimo en Java, sin frameworks, capaz de servir archivos estáticos y exponer una API REST sencilla para gestión de tareas.

## Comenzando

Estas instrucciones te permitirán obtener una copia del proyecto y ejecutarlo en tu máquina local para desarrollo y pruebas.

### Prerequisitos

* Java 8 o superior
* Maven
* Browser

## Instalando

1. Clona el repositorio
   ```
    git clone https://github.com/DavidBarbosag/tallerDisenoEstructuracionAplicacionesInternet.git
   ```

2. Entra al directorio del proyecto
3. Compila el proyecto con Maven
   ```
     mvn clean package
   ```
4. Ejecuta el servidor
  ```
    java -cp target/http-mini-server-1.0-SNAPSHOT.jar http.SimpleHttpServer
  ```
5. Accede mediante este url http://localhost:35000.


## Estructura del proyecto

```
http-mini-server/
├── assets/                          # Imágenes y recursos estáticos para la documentación
│   ├── exampleStaticFiles.png
│   ├── img.png
│   └── taskSended.png
│
├── public/                          # Archivos estáticos servidos por el servidor
│   ├── index.html
│   ├── style.css
│   ├── app.js
│   └── img/
│       └── test.jpg
│
├── src/
│   ├── main/
│   │   └── java/
│   │       └── http/
│   │           ├── SimpleHttpServer.java
│   │           └── Task.java
│   │
│   └── test/
│       └── java/
│           └── http/
│               └── AppTest.java
│
├── pom.xml                          # Archivo de configuración de Maven
├── README.md                        # Documentación del proyecto
└── target/                          # Archivos compilados y generados por Maven
```

## Arquitectura

Arquitectura
El servidor HTTP está construido en Java sin frameworks externos. Su arquitectura se compone de los siguientes módulos:


* Servidor principal (SimpleHttpServer.java):

   Gestiona las conexiones entrantes, sirve archivos estáticos desde la carpeta public/ y expone una API REST para la gestión de tareas.


* Modelo de datos (Task.java):

   Representa las tareas gestionadas por la API, permitiendo operaciones de consulta y creación.


* Recursos estáticos:

   Los archivos HTML, CSS, JS e imágenes se encuentran en la carpeta public/ y son servidos directamente por el servidor.

  
El flujo básico consiste en recibir una solicitud HTTP, identificar si es para un recurso estático o para la API,
y responder en consecuencia. La comunicación entre módulos se realiza mediante clases Java simples, facilitando la extensión
y el mantenimiento.

## Uso

* Para ver la página principal:
http://localhost:35000/

![Página principal](assets/img.png)

* Al agregar una tarea, se muestran en la lista de tareas.

![Tarea Enviada](assets/taskSended.png)

* Para consultar las tareas (API):
http://localhost:35000/api/tasks

* Para mostrar los archivos estáticos:
http://localhost:35000/<ruta_del_archivo>
    (Muestra el contenido del archivo si existe).

![Archivo estático](assets/exampleStaticFiles.png)


## Authors
David Alfonso Barbosa Gómez

   
