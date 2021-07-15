# Creando proyecto React
Creación de un proyecto en *React* utilizando *TypeScript*

## Configuración de ambiente
1. Creación del proyecto
~~~powershell
   npx create-react-app <proyecto> --typescript
~~~
2. Instalación de router DOM
~~~powershell
   npm i react-router-dom
   npm i @types/react-router-dom
   npm i --save-dev @types/react-dom
~~~   
3. Instalación de material
~~~powershell
   npm install @material-ui/core
   npm install @material-ui/icons
~~~
4. Instalación de fuente roboto y utilización de iconos en el archivo public/index.html, al interior de la etiqueta *head*
~~~html
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Roboto:300,400,500,700&display=swap"/>
    <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons" />
~~~
5. Realizamos importación de modulo para el consumo de backend axios
~~~powershell
   npm i axios
~~~
   