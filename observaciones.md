# Observaciones

Carla, felicitaciones por tu trabajo. Tu portfolio está muy hermoso, y se nota mucho el esfuerzo por lograr un trabajo con personalidad propia que a la vez cumpla las consignas y el diseño propuesto. El resultado es una web que te refleja y a la vez cumple a la perfección lo solicitado.

Tengo, lamentablmemente, pocos comentarios para hacerte, ya que el nivel de este trabajo es realmente muy alto. Pero siempre hay algo que comentar! :) Como dije en clase, este trabajo no se hace para que constates conocimientos, sino para que aprendas: en ese sentido, mi intencion es que estos comentarios te sirvan para aprender, mejorar tu codigo a futuro e ir apreciando mejor qué se espera de nosotras como desarrolladoras front end.

## Estructura correcta de documento HTML

Tu HTML esta realmente excelente. Claro, prolijo, muy bien comentado e identado.

Algo que me llama la atención es tu `header`, dado que allí repetís innecesariamente muchísimos links. Cosas como esta se repiten un montón:

```html
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.8.2/devicon.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.8.2/devicon.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.8.2/devicon.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.8.2/devicon.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.8.2/devicon.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.8.2/devicon.min.css">
```

Cada uno de esos links hace exactamente lo mismo - traerse el css de devicons para poder usar los íconos en tu sitio. Quizá estés bajo la impresión de que por cada uno de los íconos de tu web es necesario traerse nuevamente el css, pero no, no es necesario agregarlo más de una vez. Agregar muchos de estos links innecesarios impacta negativamente en la velocidad de carga de tu web, ya que por cada uno de ellos se hace un llamado a un css externo y se lo carga. 

Tenés tendencia a agregar divs innecesarios. Considerá por ejemplo el div con la clase "container". Lo unico que hace es medir el 100% de su contenedor al ancho y  lo largo, cosa que ya hacen por defecto los divs. Podrías borrarlo sin consecuencias. 

Utilizás ocasionalmente etiquetas `br` para separar las cosas: no llegué a comentarlo en clase, pero esto es incorrecto. Esa etiqueta es un resabio de viejas épocas en las cuales css no era tan poderoso como ahora, pero usarla hoy viola uno de los principios básicos de programación: la separación de responsabilidades. Los estilos se dan con css, la estructura se da con html. Una decisión de estilo como un espaciado entre dos elementos debe controlarse con css -flex, elementos en bloque, etc, no con `br`. 

## Respeta la consigna

- El portfolio cuenta con las secciones solicitadas
- Al clickear en los links de navegación, debe llevar a la sección correspondiente
- Al clickear en los links de contacto, debe llevar a la página externa
  correspondiente
- El portfolio debe tener un diseño responsivo y verse correctamente en distintos dispositivos
- El portfolio debe estar deployado y ser accesible desde una URL
- El repositorio en GitHub debe tener un readme adecuado

Todos estos puntos están cumplidos. Menciono especialmente tu responsive: es increíble lo bien que solucionaste las distintas resoluciones, siguiendo casi a la perfección el modelo y preocupandote para que todo se vea hermoso, veamos tu web desde cualquier dispositivo. Lo lograste además con muy poquitas media queries, lo cual es fantástico.

### Respeta el diseño dado

Cumplido a la perfección, con la excepción del nav en donde el link de contacto está desalineado con respecto a los demás. Se soluciona con un `align-items: center;` en .navMenu.


### Buena estructura de proyecto

Cumplido. Cuidado con los archivos que tienen mayúscula en el título, algo que podría traerte problemas en el linkeado. Está bien que hayas puesto las imágenes en assets, pero la excepción a esta regla es el favicon, que siempre debería ir en la carpeta principal. Atención también a su nombre: debería estar en minúscula. 

### Código bien indentado

Tabulas muy bien, lo cual parece un detalle extra cuando una recien comienza pero ayuda un monton a su legibilidad, y que lo hayas logrado en esta etapa es un gran mérito. 

### Comentarios que permiten mejorar la legibilidad del código

Impecables en HTML, lamentablemente ausentes en CSS, donde vendrían bien para separar los estilos de casa cosa.

Noto que tenés mucho codigo comentado. Esto no es buena práctica, es el equivalente de tachar algo en un texto impreso para la facu. Mejor borrarlo. No debería haber código comentado en una entrega a menos que sea un mensaje para otros desarrolladores o una indicación de secciones. 

### Uso correcto de etiquetas semánticas

- Me llama la atención que hayas usado `div` para las tarjetas de Mis Conocimientos y Mis Proyectos: yo diría que deberían ser `article`. Pero es el único detalle a comentar aquí (y hay quien podría discutirme que deberían ser divs)

- Usas mas de un `h1` en tu web. El h1 es el titulo principal, y debería haber sólo uno por página. El resto deberían estar en orden de jerarquía: h2 para los titulos de secciones, h3 para los títulos dentro de cada subsección, etc. En este caso, "Mis conocimientos", "Mis proyectos" etc deberían ser h2 y los títulos de las cards deberían ser h3. 

- Como vimos en la clase de accesibilidad, los lectores de pantalla dependen de la etiqueta `nav` para mostrarle la barra de navegación al usuario, así que deberías tener un `nav` en la primera barra de navegación en lugar de `header`. 

- Usas `button` para cosas que son links. 

### Buenos nombres de clases

No usamos mayúsculas en HTML o CSS. Cuando quieras separar palabras, como en "navBar", escribilo con guiones: "nav-bar". 

Muchas veces tus nombres de clases no son descriptivos en sentido funcional. Idealmente, debería poder leer el CSS sin ir a mirar el HTML, porque tus nombres de clases me indicarían claramente qué es cada cosa. En tu TP tuve que hacerlo muchas veces. Tomá por ejemplo esta serie de nombres: cardSection1, card2, formCopy, titleCard2. Es muy difícil saber qué es cada cosa. Si tus tarjetas de proyectos y conocimientos son diferentes, lo correcto es mencionar su función en el nombre de clase: "projects-card", "skills-card". 


### Código CSS bien estructurado

Cumplido a nivel formal. Noto algunos estilos innecesarios o confusos, que te voy indicando en tu archivo de css.

### Reutilización de estilos

Cumplido en general, veo mucho interés por eso. Ocasionalmente tenés clases diferentes para el mismo estilo. titleCard1, .titleCard2, tienen el mismo estilo. Deberían ser la misma clase. 

### Cumple con criterios básicos de accesibilidad

- Los colores tienen un contraste adecuado

Incumplido, el color de texto #FEBAAF no es apropiado para ser usado con un fondo blanco. Siempre chequea con herramientas del tipo https://webaim.org/resources/contrastchecker/

- Las imágenes tiene el atributo `alt` que corresponde

Incumplido, los alt están vacíos. Eso sólo vale para imágenes decorativas. "Imagen programadora" aclara que es una imagen, algo que el usuario ya sabe, y no describe adecuadamente la imagen: "Mujer con una computadora" sería más adecuado aquí. 

- Los íconos y elementos que no presentan texto agregan la información correspondiente por otros medios (etiquetas aria, texto oculto)

No cumplido, por ejemplo en los links a redes sociales de tu footer. Necesitan un aria.

- Los íconos y elementos que no necesitan ser anunciados por un lector de pantalla tienen la etiqueta aria
  correspondiente

No cumplido. 

- Commits con mensajes adecuados

Cumplido, noto muchos y buenos commits en tu proyecto, lo que siempre se agradece.

- Cuenta con un favicon

Cumplido, aunque debería estar en la carpeta principal y con la capitalización indicada. 

### Nota: 8
