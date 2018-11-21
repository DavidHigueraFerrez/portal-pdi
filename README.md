

# Portal PDI

## Descripción
Portal del PDI de la ETSIT desde el que pueden acceder a todas las aplicaciones disponibles, estando añadida la funcion de SSO para no tener que hacer login cada vez que cambian entre aplicaciones.
El portal a su vez es desde donde se sirven al resto de aplicaciones del portal, la libreria javascript que permite crear el menu lateral en el resto de aplicaciones

## Ejecución
El proyecto esta desarrollado en node, para poder correrlo continuadamente hemos usado la libreria forever

```
forever start app.js
``

## Menu Lateral
A nivel de /portal-pas estan disponibles los ficheros javascript que sirven los menus laterales, desde dichos ficheros redirige haciendo SSO al resto de aplicaciones del portal y permite hacer log out en todas las aplicaciones a la vez

#### Ficheros button-static-[aplicacion].js
Los ficheros javascript que siguen este nombre son los menus laterales preparados para las aplicaciones configurados para el CSS de cada aplicacion. 
Se pueden insertar en las aplicaciones mediante las siguientes instrucciones

### Insertar Menu Lateral en el resto de aplicaciones
1º Insertar el script disponible en https://dev.etsit.upm.es/portal-pdi/button-static-[aplicacion].js 

Ejemplo

```
<script src="https://dev.etsit.upm.es/portal-pdi/static-button-inter"></script>
```

2º Crear un div con id unico donde poder insertar el menu lateral, intentar insertarlo en el html en el lugar del boton de logout.

Ejemplo

```
 <div id="buttonStatic"></div>
```

3º Llamar a la funcion dibujarMenuLateral("buttonStatic"); indicando el id del div donde quieres añadir el menu.
```
$(document).ready(function(){
    dibujarmenulateral("buttonStatic");
});
```

## Nota adicional
Cualquier problema de que el estilo del menu lateral no sea el adecuado a la aplicacion notificar
Aplicacion disponible en (https://dev.etsit.upm.es/portal-pdi) siempre que estes dentro de la red Eduroam
