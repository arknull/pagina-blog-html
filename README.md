# pagina-blog-html
*Este proyecto es la maquetación de una página de blog usando html y css. *

Se establece la guía para mantener y escalar el proyecto.

## Estructura de carpetas
En la carpeta principal está el index.html y el index.css para facilitar la lectura por el navegador. Los demás archivos están almacenados en carpetas agrupado por su tipo y función.

**img**			*contiene las imágenes*
index.html
main.css

## Layout
Es un Layout tradicional, se construye siguiendo el flujo de la página. Se divide en Header, card, articles section, card y footer.
- Header: contiene los links a las secciones del sitio. Es una barra de navegación horizontal.
- card: contiene un articulo destacado. Esta conformado por una imágen y una descripción.
- Articles-section: resume articulos recientes.
- Footer: contiene los links a las redes sociales.

Se compone a partir de componentes flexibles.

## Componentes
Los componentes se organizan basados en los articulos. 
Se usa BEM para establecer las clases de los elementos. El bloque es el artículo o sección y los elementos son descriptivos. 

**Para mejorar la accesibilidad todas las imágenes deben tener su descripción en el atributo alt**

### Header
```html
  <header class="header">
    <a href="/" class="header__link">Home</a>
    <a href="/" class="header__link">Acerca de</a>
    <a href="/" class="header__link">Portfolio</a>
    <a href="/" class="header__link">Blog</a>
    <a href="/" class="header__link">Contacto</a>
  </header>
```
### Card
```html
<div class="card">
  <div class="card__content">
    <h3 class="card__category-title">Entrada destacada</h3>
    <h2 class="card__title">Crea un sitio web usando HTML5</h2>
    <p class="card__description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum inventore dolores quibusdam quasi placeat nam quam vero perferendis totam, a sapiente ducimus quaerat, eaque ipsam harum veritatis provident exercitationem dignissimos earum, nostrum nobis itaque cumque. Nisi ullam magnam perferendis necessitatibus odit, id quod maiores ipsam, architecto facilis cupiditate a adipisci.</p>
  </div>
  <img class="card__img--frame" src="img/couple.jpg" alt="Picture of a couple watching you">
</div>
```
### Article Card
```html
  <div class="article-card">
    <p class="article-card__metadata">El 29 de octubre de 2012<br/>Por <span class="article-card__meta-name">Ernesto G Bustamante</span><br/><small class="article-card__meta-comment">3 comentarios</small></p>
    <div class="article-card__content">
      <h2 class="article-card__title">Las bondades de HTML5</h2>
      <p class="article-card__description">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Deserunt dolore libero quis exercitationem. Eaque sit, ipsum, esse culpa iusto voluptatum consequuntur eos expedita quas quod omnis dolorum modi perferendis optio praesentium perspiciatis nemo ullam corrupti et repellat non veritatis ducimus dolore. Dolore distinctio facere quisquam, adipisci earum quia omnis minus reiciendis beatae quam voluptatum dolorum deserunt ex officia repudiandae neque temporibus excepturi non consequatur amet repellat minima? Consequuntur, distinctio laudantium! Modi ipsa ut voluptate eius dolorem porro mollitia praesentium cum quis at, officia, repudiandae nesciunt excepturi architecto. Sint in sequi labore hic, delectus beatae maxime explicabo porro, autem fuga minus!</p>
      <a href="/" class="article-card__link">Leer más</a>
    </div>
  </div>
```
### Footer
```html
<footer class="footer">
  <div class="footer__social">
    <a class="footer__social-link" href="">
      <img src="https://img.icons8.com/color/48/000000/twitter-circled.png" />
    </a>
    <a class="footer__social-link" href="">
      <img src="https://img.icons8.com/color/48/000000/facebook-new.png" />
    </a>
    <a class="footer__social-link" href="">
      <img src="https://img.icons8.com/color/48/000000/spotify.png" />
    </a>
    <a class="footer__social-link--youtube" href="">
      <img src="https://img.icons8.com/color/48/000000/youtube-squared.png" />
    </a>
  </div>
  <p>© 2012. Todos los derechos reservados</p>
</footer>
```

## Variables
Para tener mayor control sobre los colores, los tipos de fuente y el espaciado, se declaran estas propiedades como variables al comienzo del documento CSS dentro de :root
```css
:root {
  /* color */
  --main-color: #C84451;
  --second-color: #D6D6D6;
  --background-color: #F4F4F6;
  --light-color: white;
  --text-color: #868682;
  /* spacing */
  --space: 10px;
  --section-spacing: 20px;
  --body-spacing: 40px;
  /* border radius */
  --border-radius: 10px;
}
```
Para llamar las variables se debe asignar a la propiedad el valor:
`var(--main-font)`

**Todos las propiedades referenciadas deben llamarse por variables.**

## Guía de estilo del código

#### HTML
Se usan etiquetas sintácticas para nombrar los elementos principales: header, main, aside.
Se cuida la indentación y el orden de los elementos siguiendo el flujo de la página.

#### CSS
Las clases se llaman usando la metodología BEM.
`bloque__elemento--modificador`
Las declaraciones se estructuran en el siguiente orden:
- Propiedades del modelo de caja
- Posicionameniento
- Tipografía
- Decoración

```css
.example-element {
  display: block;
  width: 220px;
  height: 40px;
  position: relative;
  font-family: var(--main-font);
  text-transform: uppercase;
  background-color: #333333;
}
```