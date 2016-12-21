## Índice
- [Introducción](#introducción)
- [Librerías de terceros](#librerías-de-terceros)
- [Páginas](#páginas)
    - [Inicio](#inicio)
    - [Galería multimedia](#galería-multimedia)
    - [Tarifas](#tarifas)
- [Banners](#banners)
- [Galerías](#galerías)
- [Vídeos fullwidth](#vídeos-fullwidth)
- [Mapas](#mapas)
- [Responsive](#responsive)


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

Para cargar imágenes con *lazy Load* debemos asignarle una imagen cualquiera en el `src` (siempre la misma y de 1x1px per ejemplo) y la imagen real en el atributo `data-src`. Al llegar a ella la imagen del `src`se sustituirá por la del `data-src`. Los elementos que deban cargarse con este sistema deben llevar la clase `class="lazy"`.

La librería detecta si se trata de una elemento `<img>` o no. En caso de no serlo cargará la imagen como background CSS.

```html
<!-- img -->
<img src="pixel.png" class="lazy" title="" alt="" data-src="/ruta/a/la/imagen.jpg" />

<!-- background-image -->
<div class="lazy" data-src="/ruta/a/la/imagen.jpg">Lorem ipsum dolor sit amet.</div>
```

## Páginas

En esta sección describiremos los aspectos a tener en cuenta en cada una de las páginas maquetadas.

### Inicio

En el slider de la cabecera hemos deshabilitado el slide de la cámara IP para IE&lt;9 debido a su incompatibilidad con el navegador.

```html
<!--[if lt IE 9]><!-->
<div class="item">
    <iframe src="http://ipcamlive.com/player/player.php?alias=5742e4ba07511&autoplay=1"></iframe>
    <div class="carousel-caption"></div>
</div>
<!--<![endif]-->
```

### Galería multimedia

Esta sección muestra distintos ploques de galerías distribuidos en `tabs` en caso de verse en desktop o en acordeón en vista móvil.

El funcionamiento de las galerías se explica en la sección [Galerías](#galerías).

```html
<!-- Tabs -->
<nav class="container text-center gallery-filter small-area">
    <ul>
        <li class="active">
			<!-- El atributo href indica el id del elemento a mostrar, data-toggle indica que es un tab de bootstrap -->
            <a href="#fotografias" class="hidden-xs" data-toggle="tab">Fotografías</a>
        </li>
        <li>
            <a href="#fotografias-bodas" class="hidden-xs" data-toggle="tab">Fotografías de bodas</a>
        </li>
        <li>
            <a href="#panoramicas" class="hidden-xs" data-toggle="tab">Panorámicas</a>
        </li>
        <li>
            <a href="#videos" class="hidden-xs" data-toggle="tab">Vídeos</a>
        </li>
        <li>
            <a href="#tour-virtual" class="hidden-xs" data-toggle="tab">Tour Virtual</a>
        </li>
    </ul>
</nav>
<!-- Contenido del Tab -->
<div class="tab-content">
	<!-- Botón del acordeón de la vista móvil -->
    <div class="visible-xs">
        <button type="button" class="b_galeria collap-btn" data-target="#fotografias">
            Fotografías
            <span class="mark"></span> 
        </button>
    </div>
	<!-- Identificador usado en el botón del Tab, las clases indican que es el contenido del tab. -->
    <div id="fotografias" class="tab-pane fade">
		<!-- Galería -->
        <div id="links-fotos" class="detalle-galeria wp-galeria" data-type="galeria-fotos" data-items="assets/img/galeria/fotos/galeria1.jpg,assets/img/galeria/fotos/galeria2.jpg">
            ...
        </div>
		<!-- Texto de la sección -->
        <div class="container detalle-galeria-info small-area">
            Lorem ipsum dolor sit amet
        </div>
    </div>
	<!-- Más tabs... -->
</div>
```

La pestaña de visita virtual es igual a las demás, sólo que en lugar de una galería, se inserta un `iframe`.

```html
<div class="detalle-galeria">
    <div class="row tour-virtual-content">
        <div class="col-md-12">
			<!-- iframe de visita virtual -->
            <iframe src="https://www.google.com/maps/embed?pb=!1m0!3m2!1sca!2sus!4v1467806620514!6m8!1m7!1sQUmuTW606IcAAAQZI8p5Ug!2m2!1d41.50740490877341!2d2.359634446464042!3f19.45!4f-11.480000000000004!5f0.5970117501821992" height="550" frameborder="0" style="border:0" allowfullscreen></iframe>
         </div>
    </div>
</div>
```

### Tarifas

En página de tarifas veremos unas flechas hacia izquierda y derecha cuando entramos en la vista móvil.

Estas flechas deberán incluirse en el código HTML de la siguiente manera.

```html
<!-- .table-tarifas[data-visible-column="2"] -->
<table class="table table01 table-tarifas" data-visible-column="2">
    <tr>
        <th></th>
        <th class="head-col">
        	<!-- Flecha izquierda -->
            <a href="#" class="visible-xs tarifas-button tarifas-button-left"> </a>
            <div class="tarifas-content">
                Del 01.01.16 a 31.05.16<br>del 01.10.16 a 31.12.16
            </div>
            <a href="#" class="visible-xs tarifas-button tarifas-button-right"> </a>
        </th>
        <th class="head-col">
            <a href="#" class="visible-xs tarifas-button tarifas-button-left"> </a>
            <div class="tarifas-content">
                Del 01.06.16 a 31.07.16<br>del 01.09.16 a 30.09.16
            </div>
            <a href="#" class="visible-xs tarifas-button tarifas-button-right"> </a>
        </th>
        <th class="head-col">
            <a href="#" class="visible-xs tarifas-button tarifas-button-left"> </a>
            <div class="tarifas-content">
                Del 01.08.16<br>a 31.08.16
            </div>
        	<!-- Flecha derecha -->
            <a href="#" class="visible-xs tarifas-button tarifas-button-right"> </a>
        </th>
    </tr>
    ...
</table>
```

Está programado de forma que busque una table con clase `table-tarifas` y muestre la, vía CSS, columna indicada en `data-visible-column`, valor que variará al pulsar las flechas.


## Banners

La imagen de cabecera se genera en un bloque de *CSS inline* para poder cargar una imagen de diferente tamaño segun el ancho de pantalla usando Media Queries.

```html
<style type="text/css">
    .banner-pagina-interior {
        background-image:url(/assets/img/banners/banner-el-hotel.jpg);
    }
    @media (max-width:767px){ 
        .banner-pagina-interior {
            background-image:url(/assets/img/banners/banner-el-hotel@xs.jpg);
        }
    }
</style>
```

## Galerías

### Contenedor

Las galerías deben estar siempre dentro de un elemento con clase `container-detalle-galeria` sin importar si es el padre directo del elemento de galería o no.

`<div class="container-detalle-galeria">`

### Configuración de la galería

A continuación deberá insertarse un elemento con clase `wp-galeria`, ID con formato #links-{nombre-dela-galeria} (puede usarse `#links` si sólo hay una galería en la página), el atributo `data-type` y el atributo `data-items` que contendrá todas las imágenes separadas por `,`:

`<div id="links" class="detalle-galeria wp-galeria" data-type="galeria-default" data-items="/assets/img/habitaciones/galeria1.jpg,/assets/img/habitaciones/galeria2.jpg,/assets/img/habitaciones/galeria3.jpg,/assets/img/habitaciones/galeria4.jpg,/assets/img/habitaciones/galeria5.jpg,/assets/img/habitaciones/galeria6.jpg,/assets/img/habitaciones/galeria7.jpg,/assets/img/habitaciones/galeria8.jpg,/assets/img/habitaciones/galeria9.jpg,/assets/img/habitaciones/galeria10.jpg,/assets/img/habitaciones/galeria11.jpg,/assets/img/habitaciones/galeria12.jpg,/assets/img/habitaciones/galeria13.jpg,/assets/img/habitaciones/galeria14.jpg">`

### ID de la galería y `data-type`

En páginas dónde sólo haya una galería de imágenes usaremos el ID `links` y `data-type="galeria-default"`.

En páginas donde haya más de una galería de fotos deberemos identificar cada una con un ID distinto y un data-type en consecuencia, por ejemplo:

```html
<div id="links-bodas" class="detalle-galeria wp-galeria" data-type="galeria-bodas">
	...
</div>
<div id="links-coches" class="detalle-galeria wp-galeria" data-type="galeria-coches">
	...
</div>
```

### Dentro de la galería

Dentro del elemento `.wp-galeria` deberemos indicar donde cargar la galería de imágenes (vista desktop - tablet) y donde cargar el carousel (vista móvil), además de añadir el botón para cargar más imágenes.

```html
<div class="gallery-content row"></div>
<div class="gallery-carousel row"></div>
<div class="text-center small-area hidden-xs">
    <a href="#" class="load-images b_generic01" data-type="galeria-fotos">Carga más imágenes</a>
</div>
```

El botón de "Cargar más imágenes" deberá tener el mismo `data-type` que su galería.

### Lazy load en 2 pasos

Para poder implementar la funcionalidad exigida de que las 6 primeras imágenes de la galería se cargaran en 2 pasos a medida que se hacia scroll hay que insertar un elemento con clase `wp-galeria` y el `data-type` correspondiente.

`<div class="wp-galeria hidden-xs" data-type="galeria-fotos"></div>`

### Maquetación de la galería

Todas las páginas que tengan una galería deben incluir en cualquier parte de la página el código HTML necesario para hacer funcionar la galería:

```html
<div id="blueimp-gallery" class="blueimp-gallery blueimp-gallery-controls">
    <div class="slides"></div>
    <a class="prev carousel-control left">
        <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
        <span class="sr-only">Previous</span>
    </a>
    <a class="next carousel-control right">
        <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
        <span class="sr-only">Next</span>
    </a>
    <a class="close">×</a>
    <a class="play-pause"></a>
    <ol class="indicator"></ol>
</div>
```

### Código completo

```html
<div class="container-fluid container-detalle-galeria">
    <div id="links" class="detalle-galeria wp-galeria" data-type="galeria-default" data-items="/assets/img/habitaciones/galeria1.jpg,/assets/img/habitaciones/galeria2.jpg,/assets/img/habitaciones/galeria3.jpg,/assets/img/habitaciones/galeria4.jpg,/assets/img/habitaciones/galeria5.jpg,/assets/img/habitaciones/galeria6.jpg,/assets/img/habitaciones/galeria7.jpg,/assets/img/habitaciones/galeria8.jpg,/assets/img/habitaciones/galeria9.jpg,/assets/img/habitaciones/galeria10.jpg,/assets/img/habitaciones/galeria11.jpg,/assets/img/habitaciones/galeria12.jpg,/assets/img/habitaciones/galeria13.jpg,/assets/img/habitaciones/galeria14.jpg">
        <div class="gallery-content row"></div>
        <div class="gallery-carousel row"></div>
        <div class="text-center medium-area hidden-xs">
            <a href="#" id="galeria-habitacion" class="load-images b_generic01" data-type="galeria-default">Carga más imágenes</a>
        </div>
    </div>
    <div class="wp-galeria hidden-xs" data-type="galeria-default"></div>
</div>
<div id="blueimp-gallery" class="blueimp-gallery blueimp-gallery-controls">
    <div class="slides"></div>
    <a class="prev carousel-control left">
        <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
        <span class="sr-only">Previous</span>
    </a>
    <a class="next carousel-control right">
        <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
        <span class="sr-only">Next</span>
    </a>
    <a class="close">×</a>
    <a class="play-pause"></a>
    <ol class="indicator"></ol>
</div>
```

### Galerías panorámicas

Su funcionamiento es el mismo que las galerías normales en la vista desktop y tablet. Sin embargo varía en la vista movil, cargado una imagen que se puede mover arrastrandola de lado a lado.

Las galerías panorámicas deben tener `data-type="galeria-panoramicas" y `id="#links-panoramicas"`.

Además deberán incluir el `<div id="panorama">` donde se cargará la imagen seleccionada en vista móvil. El texto que contenga este div se mostrará cuando no haya ninguna foto seleccionada.

```html
<div id="panoramicas" class="tab-pane fade">
    <div id="links-panoramicas" class="detalle-galeria wp-galeria" data-type="galeria-panoramicas" data-items="assets/img/galeria/panoramicas/01.jpg,assets/img/galeria/panoramicas/02.jpg">
        <div id="panorama" class="panorama visible-xs"><p class="help-text">Pulse sobre una imagen y deslice el dedo sobre la foto para ver la imágen panorámica.</p></div>
        <div class="gallery-content row"></div>
        <div class="text-center small-area">
            <a href="#" class="load-images b_generic01" data-type="galeria-panoramicas">Carga más imágenes</a>
        </div>
    </div>
</div>
```

### Galerías YouTube

Para crear una galería de vídeos de YouTube, ésta deberá tener `id="links-videos"` y `data-type="galeria-videos"`.

Dentro del atributo `data-items` hay que insertar los IDS de los vídeos separados por comas.

```html
<div id="links-videos" class="detalle-galeria wp-galeria" data-type="galeria-videos" data-items="7HQLebqlBUM,TcHfdG2CzsQ,WZnu4SnAbRE,PE2_i4xR6gc">
```

## Vídeos fullwidth

Para insertar vídeos de YouTube que ocupen todo el ancho de pantalla hay que insertar el siguiente código:

`<div id="container-video" data-url="https://www.youtube.com/embed/ID_DEL_VIDEO"> </div>`

## Mapas

Para insertar un mapa de Google Maps centrado en la dirección del Hotel hay que insertar el siguiente código:

`<div id="map"></div>`


## Responsive

Se han modificado las Media Quieries por defecto de Bootstrap quedando de la siguiente manera:

- XS (<768px)	
- SM (≥768px)
- MD (≥992px)
- LG (≥1000px)