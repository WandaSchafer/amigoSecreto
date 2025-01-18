# Amigo Secreto 
## Propósito 
El propósito de este proyecto es ofrecer una solución práctica para organizar sorteos de amigo secreto. También sirve como un ejemplo práctico de cómo usar JavaScript para manipular el DOM y manejar eventos.


## Funcionalidades 
1. Agregar nombres:
   - Los usuarios pueden escribir nombres en un campo de texto y agregarlos a una lista visible en la página.
   - Se valida que el campo de texto no esté vacío antes de agregar un nombre.
2. Visualización de la lista:
   - Los nombres ingresados se muestran dinámicamente en una lista debajo del campo de entrada.
3. Sorteo aleatorio:
   - Un botón "Sortear Amigo" selecciona un nombre aleatorio de la lista y muestra el resultado en la página.
4. Accesibilidad:
   - La página está diseñada para ser accesible con atributos como `aria-live` y etiquetas semánticas.

## Estructura del proyecto 


### Archivos principales
- index.html: Contiene la estructura HTML de la aplicación.
- app.js: Implementa la lógica principal del sorteo y la gestión de la lista.
- style.css: (Opcional) Archivo de estilos para personalizar la apariencia del proyecto.
  

### Explicación del código principal
- Selección de elementos DOM: 
   Se utiliza `document.getElementById` para interactuar con los elementos de la página, como el campo de entrada, la lista de amigos y la sección de resultados. Esto permite capturar y manipular elementos HTML desde JavaScript de manera sencilla.
- Gestión del array amigos: 
   Este array se usa para almacenar los nombres ingresados por el usuario. Es modificado usando el método `push` para añadir nombres y `Math.random` combinado con `Math.floor` para seleccionar un elemento de forma aleatoria. Este enfoque garantiza una selección justa y eficiente.
  
   ```javascript
   const indiceAleatorio = Math.floor(Math.random() * amigos.length);
   const amigoSeleccionado = amigos[indiceAleatorio];
   ```
- Validaciones: 
   Se emplea el método `trim()` para eliminar espacios en blanco al inicio y al final del texto ingresado. Esto asegura que los nombres no contengan errores debido a espacios accidentales.

   ```javascript
   if (inputAmigo.value.trim() === "") {
       alert("Por favor, ingresa un nombre válido.");
   }
   ```
- Manipulación del DOM: 
   Al agregar un nombre, se crea dinámicamente un elemento `<li>` con `document.createElement` y se añade al contenedor de la lista utilizando `appendChild`. Este método permite que la lista se actualice en tiempo real.

   ```javascript
   const listItem = document.createElement('li');
   listItem.textContent = nombre;
   listaAmigos.appendChild(listItem);
   ```


## Posibles problemas y soluciones 
1. **Los nombres no se agregan a la lista**:
   - Verifica que el campo de entrada no esté vacío.
   - Asegúrate de que el archivo `app.js` esté correctamente enlazado en el HTML.

2. **El sorteo no funciona**:
   - Comprueba que hay nombres en la lista antes de intentar realizar el sorteo.
   - Revisa la consola del navegador para identificar posibles errores.


## Mejoras futuras 
- Permitir eliminar nombres de la lista.
- Implementar almacenamiento local (`localStorage`) para persistir los datos.
- Agregar soporte para establecer un límite máximo de participantes.
- Mejorar el diseño visual y añadir animaciones para el sorteo.



