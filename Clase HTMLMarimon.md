11/17/2017 6:38:57 PM 

# Clase HTML /// *Profesor Arturo Marimón*


![Servidor Web](http://media02.hongkiat.com/accessible-local-web-server/localtunnerl-cover.jpg)

### HTTP
HTTP es el protocolo de comunicación que permite las transferencias de información en la WorldWide Web. Así tú puedes navegar por las webs (al igual que Googlebot).

### HTTPS

Es un protocolo de aplicación basado en el protocolo HTTP, destinado a la transferencia segura de datos de Hipertexto, es decir, es la versión segura de HTTP.

### HTTP/2
Protocolo binario con conexión única. El servicio “server push”5​ también conocido como “cache push”, se basa en estimaciones para que el servidor sea capaz de enviar información al usuario antes de que éste la solicite para que la información esté disponible de forma inmediata.

## Tipos de respuestas que da el servidor:



Al pedir un *Algo* a un site el servidor te manda una respuesta según código:

1. 1XX Informacional
2. 2XX Found
3. 3XX Redirecciones
	+ 301 Lo que buscabas aquí está ahora en otro sitio :-)  / Pasa todo el LinkJuice 
	+ 302/ 307 Lo que estaba aquí ahora no está, pero quizás vuelva :-) :-)  La autoridad se queda en A, pero coge contenido de B
4. 4XX Error  
  + 404 Error not found 
  + 410 Elemento ya no existe
5. 5XX *El Servidor Peta* 
  + 500 Condición inesperada
  + Error temporal // Servidor No disponible

#### Dependiendo del error decidimos solucionarlo o dejarlo con, ¡*Huye, error!*
## ¿Cómo hacer una redirección?
Se hace a través del fichero de configuración Apache **.htaccess** ![Ojo! Mejor no tocarlo](http://www.i2clipart.com/cliparts/b/d/6/8/clipart-warning-icon-bd68.png)

¡Pero mejor no tocarlo y delegar en una empresa de servidores!

A través de expresiones regulares en el  archivo podemos ordenar redirecciones para nuestro site.
  -> [Web de testeo para htaccess](http://htaccess.mwl.be/)

## ¿Cómo no hacer la redirección?
+ Evitar las redirecciones desde una página --> *Meta Refresh*. Es más lenta, no pasa todo el Link Juice. 

#### Contenido Eliminado
*Ejemplo*: Si tenemos un producto ya descatalogado o sin Stock

*Soluciones* 404 o 301 a producto /cartegoría o mantenerlo y eliminarlo de búsquedas internas (200), dando alternativas hasta que se reponga.

#### Posibles soluciones
 + Intentar no borrar el contenido (404) 
 + Redireccionar a otro producto o categoría 
 + Mantener el producto y eliminar listados y busqueda internas (200)
 + La página da alternativas a la búsqueda realizada (200)

### Robots.txt
![Robot](https://icons8.com/iconizer/files/Human_o2/orig/gnome-robots2.png)

+ **user-agent:bot** - Identifica el bot al que va dirigida.
+ **disallow:Path** - Bloquea la ruta indicada.
+  **allow:path** - permite la ruta indicada.
+  **sitemap:url** - indica la ruta del sitemap

Cuando bloqueas el acceso a un robot de google no desaparece de los buscadores, tarda varios meses en hacerlo.

*Algunas Cosinas*:

+ Acepta expresiones regulares.
+ No bloquees acceso a los CSS ni JS
+ Añade tu sitemap
+ Tamaño máximo: 500Kb
+ Sólo afecta al dominio en le que se encuentra
+ En caso de contradicción la regla más específica predomina sobre la más general. --> Disallow: /Scripts/   &   Allow: /Scripts/*.js  **Se bloqueará el contenido de /Scripts/ excepto los ficheros .js

[**Ejemplo Robots**](http://www.marketingonlinevalencia.com/robots.txt)

### Sitemaps 
+ Puede ser HTML : *No se debe usar , es en caso de una arquitectura web muy mala.*
+ Puede ser XML  : *El habitual*

El sitemap te ayudará a indexar contenido más rápidamente 

### Title
Completar con las diapositivas
+ Poner siempre tu nombre de marca. En la home debe ser la primera palabra.
### Metadescripton
+ No tiene ningún valor para el posicionamiento, pero sí en el CTR.
+ El límite de caracteres visibles es de 150
+ Call to Action!

11/18/2017 9:59:20 AM 

### Metas en general  
Dan información a los buscadores y los navegadores. Hay infinitos. No influyen en el posicionamiento, Google no los lee.
##### Algunas relevantes:
###### HEAD

    <meta name="Robots" content="noindex, nofollow">
Te desindexa un contenido, aunque consume crawls.

    <link rel="alternate" hreflang="Idioma-Pais" href="URL"/>
Ayuda a los buscadores a mostrar el contenido adecuado para las diferentes localizaciones. 

    <link rel="canonical" href="htttp://www.example.com/page"/>
Indicas a Google cual es el contenido original en caso de contenido original. Google podría ignorar un canonical. Una redirección 301 funcionaría seguro.

    <link rel="alternate" media="print" href=“versión_impresora.html" />
Define la relación del documento con un elemento externo o alternativo.

    <link rel="prev" href="anterior.html">
Dice al nevegador la página anterior la página actual. Rel="next" para indicar la siguiente.

    <link rel="author/me/publisher" />
Te vincula en la serp a tu cuenta de G+
###### BODY
Se busca hacerlo fácil para el usuario y el buscador.
Fauna de un body:

    <a href= "http://www.example.com" title = "A link to an example" >

 + Links: Con su correspondiente html Link
 + Anchor text:  El texto del enlace en el que haces click

    <img src="https://misanimales.com/wp-content/uploads/2016/10/crecen-los-gatos.jpg" alt="Cuenco de sopa de tomate" />

    ```<img src="https://misanimales.com/wp-content/uploads/2016/10/crecen-los-gatos.jpg" alt="Cuenco de sopa de tomate" />
	```
 + Imágenes: El alt-text da información sobre la imagen de nuestra web, a veces Google sabe de que va la imagen (especialmente si es de banco de imágenes y se usa frecuentemente en campos concretos). 
 + Información tabluda en tablas ```<table>```
	 + Descripción corta del propósito de la tabla```<caption>```
	 + Una descripción más larga de la tabla ```<summary>``` 
 + Enlaces con ```<a rel="nofollow">```  
	 + No se deben hacer interno
	 + Se usa para enlaces de pago. 

Para la página [El gato con botas](www.animales.com) enlaza a animales.com

	+ El gato con botas es el anchor text
	+ El enlace es animales.com

+ Esquemas y microdatos: Añade "Rich Snippets" en la SERP
```<div> itemscope itemtype="www.bkbakb.com" </div>``` (Comprobar)

No se pueden mezclar esquemas, sino no aparecen "Rich Snippet"

```<aside> </aside>``` Relacionado a un contenido sin ser parte del contenido
```<article> </article>``` Unidades independientes con estructuras propios en su web. 
<img src="http://www.homeandlearn.co.uk/WD/images/chapter6/article_html5.gif" alt="Ejemplo de Article" />
Ejemplo de ```<article>``` 

```<section>```  
Sección del contenido relacionado. La suma de loss ections construyen la unidad. Su funcionalidad principal es estructurar semánticamente un documento a la hora de ser representado. [Más info](http://html5doctor.com/the-section-element/ "Más info")

```<mark>``` 
El elemento <mark> sirvepara destacar términos de relevancia actual o para destacar partes de contenido sobre las que se quiere llamarla atención, pero cuyo significado semánticono se quiere cambiar.

```<role></role>``` Su misión es definir el papel que juegan los elemento dentro del documento web


``<main role="main"></main>`` Etiqueta importante para el SEO, ayuda al navegador a centrarse en el  contenido importante de una página de la morralla (Cookies, menú y blablabla) 
Su misión es definir el papel que juegan los elemento dentro del documento web
