## Índice
- [Introducción](#introduccion)
- [Librerías de terceros](#librerias-de-terceros)
- [Páginas](#paginas)
    - [Inicio](#inicio)
    - [Habitaciones](#habitaciones)
    - [Detalle Habitación](#detalle-habitacion)


## Introducción

En esta guía trataremos de mostrar los aspectos básicos de funcionamiento de la maquetación llevada a cabo para el Hotel Montíboli con el objetivo de facilitar su integración con el CMS pertinente.

## Librerías de terceros

##### Bootstrap v3.3.7 - [Docs](https://github.com/twbs/bootstrap)

##### jQuery v.12.4 - [Docs](https://github.com/jquery/jquery)

##### html5shiv v.7.3 - [Docs](https://github.com/aFarkas/html5shiv)

Habilita el uso de elementos de HTML5 en IE<9

##### respondJs v.4.2 - [Docs](https://github.com/scottjehl/Respond)

Habilita el uso de Media Queries de HTML5 en IE<9

##### jquery-placeholder v.3.1 - [Docs](https://github.com/mathiasbynens/jquery-placeholder)

Usada para añadir la la funcionalidad del atributo de HTML5 [`placeholder`](http://www.anerbarrena.com/placeholder-html5-3971/) en navegadores que no lo soportan

##### moment v2.17.1 - [Docs](http://momentjs.com/docs/)

Librería JS de manipulación de fechas

##### waypoints v4.0.1 - [Docs](http://imakewebthings.com/waypoints/guides/jquery-zepto/)

Librería JS para lanzar funciones al hacer scroll a un elemento

##### mobile-detect v1.3.5 - [Docs](http://hgoebl.github.io/mobile-detect.js/)

Detección del dispositivo del usuario a través del User-Agent. Usado para emular la vista tablet en tablets con una resolución mayor a 1000px de ancho

##### jquery-parallax v.1.1.3 - [Docs](https://github.com/IanLunn/jQuery-Parallax)

Efecto parallax en imágenes de background

##### jquery-date-range-picker v.0.14.2 - [Docs](https://github.com/longbill/jquery-date-range-picker)

Librería usada en el calendario de reserva. Calendario para elegir rangos de fechas.

##### blueimp-gallery v.2.22.0 - [Docs](https://github.com/blueimp/Gallery)

Galería de imágenes y vídeos apta para desktop y dispositivos táctiles

##### eonasdan-bootstrap-datetimepicker v.4.17.43 - [Docs](https://github.com/Eonasdan/bootstrap-datetimepicker)

Calendario para inputs de fecha

##### unveil2 v.2.0.6 - [Docs](https://nabble.github.io/unveil2/)

Lazy load para imágenes y imágenes de background

Para cargar imágenes con *lazy Load* debemos asignarle una imagen cualquiera en el `src` (siempre la misma y de 1x1px per ejemplo) y la imagen real en el atributo `data-src`. All llegar a ella la imagen del `src`se sustituirá por la del `data-src`. 

La librería detecta si se trata de una elemento `<img>` o no. En caso de no serlo cargará la imagen como background CSS.

```html
<!-- img -->
<img src="pixel.png" title="" alt="" data-src="/ruta/a/la/imagen.jpg" />

<!-- background-image -->
<div data-src="/ruta/a/la/imagen.jpg">Lorem ipsum dolor sit amet.</div>
```


You can use the [editor on GitHub](https://github.com/AtoomStudio/montiboli-docs/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/AtoomStudio/montiboli-docs/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
