# Creando proyecto NODEJS

A continuación esto son los pasos que debemos de seguir para crear el proyecto en NODEJS

[Curso base](https://www.youtube.com/watch?v=_RZ-T6TxP7w&list=RDCMUCX9NJ471o7Wie1DQe94RVIg&start_radio=1&rv=_RZ-T6TxP7w&t=17&ab_channel=FaztCodeFaztCode)

## Configuración del ambiente

1. Iniciamos aplicación, con la instrución *npm init* se genera el archivo *package.json* el cual contiene la descripción de nuestra apliación
~~~powershell
   npm init -y
~~~
2. Debmos realizar instalación de dependencias para ello utilizamos las siguientes instrucciones:
~~~powershell
   npm i express mongoose morgan dotenv cors
~~~

   * **express:** Framework que nos permite la creción de API
   * **mongoose:** dependencia que nos permite realizar conexión a base de datos mongo
   * **morgan:** permite visualizar las peticiones que van llegando
   * **dotenv:** Permite administrar variables de entorno de la aplicación
   * **cors:** Dependencia que me permite exponer el servicio a un frontend

3. Realizamos instalación de dependencias *TypeScript* para poder dar manejo en el ambiente de desarrollo a nuestra construcción
~~~powershell
   npm i -D typescript @types/express @types/morgan @types/mongoose @types/cors @types/node ts-node-dev
~~~

4. Creamos carpeta src al interior de nuestro proyecto.
5. Puesto que vamos a trabajer con TypeScript, debemos de crear el archivo tsconfig.json, para ello utilizamos el siguiente mandato
~~~powershell
   npx tsc --init
~~~
Luego realizaremos las siguientes configuraciones en el archivo tsconfig.ts
* "target": "es6"
* "rootDir": "./src"
* "outDir": "./dist"

Adcional, vamos a crear un nuevo script en nuestro package
* "bulid":"tsc"
* "dev":"ts-node-dev src/index.ts"

### Plugins de VSCode
* ES7

### Añadir servidor https
Es importante crear la posibilidad de que los servicios de nuestra aplicación se expongan mediante https, para ello vamos a seguir los siguientes pasos

Vamos a instalar de una vez las demás dependencias: *https* para el manejo del servidor con SSL y *fs* para acceso al sistema de archivos.
~~~
npm install --save fs
npm install --save https
~~~

Para crear un servidor web https necesitamos los archivos de los certificados SSL (crt y key) para el dominio que vamos a utilizar o podemos crear un certificado de pruebas autofirmado con [OpenSSL](https://www.openssl.org/) nada más para desarrollar nuestro servidor y na vez concluido y probado reemplazamos los archivos crt y key por los que correspondan al servidor donde vamos a desplegar el proyecto.

Una vez creados los archivos del certificado autofirmado, los copiamos en la carpeta del proyecto: mi_certificado.crt y micertificado.key, (este último se puede convertir a .pem y funciona sin problema).

[Como crear un certificado autofirmado](https://www.youtube.com/watch?v=KA0M0xqQ0F0&ab_channel=RodolfoBorja)

## Construcción del servicio
Para la construcción del servicio vamos a arquitectar toda la estructura que nos permitira dar manejo a el funcionamiento de nuestra aplicación.
