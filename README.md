# Conditional Profile Card - Entregado el 13/11/21 ✅


## Acerca de este proyecto


- Trabajaremos con una serie de inputs y selects para editar nuestra "Profile Card" en tiempo real. Mediante código Javascript tomaremos estos valores de los inputs y se lo iremos asignando a nuestra tarjeta.   



## 1. 😵 ¿Cómo comenzar?


- Opción nº1: Haz click en el botón de abajo para abrir este repositorio en tu Gitpod.


[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io#https://github.com/ManuuMT/exercise-conditional-profile-card.git)


- Opción nº2: Puedes clonar este repositorio desde la consola de Gitpod con el siguiente comando:

```sh
git clone https://github.com/ManuuMT/exercise-conditional-profile-card.git
```



## 2. Cómo abrir el proyecto


Antes de comenzar deberás instalar los paquetes necesarios para poder compilar el proyecto. Para esto debes ingresar por la consola los siguientes 2 comandos en este mismo orden:


```sh
npm install

```

```sh
npm run start
```

> Aclaración: Antes de ejecutar estos comandos debes ingresar por consola a la carpeta perteneciente al proyecto, para esto: 

```sh
cd exercise-conditional-profile-card
```



## 3. 📋 Instrucciones 

- Nuestro código se compone de 3 partes:

`Primera parte: `  
```js
function render(variables = {}) {
// Aquí se encuentran los operadores ternarios que cambian los valores de las variables que construirán nuestra Profile Card

// Más abajo dentro de la misma funcion, añadimos estas variables en nuestro código HTML 
// por medio de interpolación de cadenas 

document.querySelector("#widget_content").innerHTML = 
`<div class="widget">
 ${cover}
... ` 
````

`Segunda parte: `

```js
window.onload = function() {
  // Creamos el objeto con las propiedades de la Profile Card y le asignamos algunos valores por defecto
  window.variables = {
    ...
    city: null
  };
  
  // Aqui llamamos a la funcion Render (la funcion que construye el HTML) 
  // para construir nuestra Profile Card por primera vez
  // y le pasamos por parámetro nuestro objeto recien creado 
  render(window.variables);  
````

`Tercera parte: `

```js
// Aqui se encuentra el Event Listener que se encarga de capturar 
// los nuevos valores en tiempo real mediante el evento "change" 
document.querySelectorAll(".picker").forEach(function(elm) {
    elm.addEventListener("change", function(e) {
    ...
    // Al final de la funcion volvemos a renderizar el objeto
    // que contiene todos los componentes de la Profile Card
    render(Object.assign(window.variables, values)); 
    }
````
