## Curso de HTML y CSS
[Pagina Principal](index.md)
Estructura basica de una pagina web
```markdown
   <body>
    <header> <!--Sección superior de nuestro website--> 
      <nav></nav> <!--Sección de navegación de nuestro website, siempre dentro del header-->
    </header>
    <main> <!--Main es el contenido central de nuestro website, "la parte del medio"-->
      <section> 
        <!--Nuestro website puede estar divido por secciones, por ejemplo platzi tiene 3: El navegador de cursos y rutas, el feed y nuestras rutas de aprendizaje-->
        <article>
          <!--Contenido independiente de la página. Es reutilizable-->
        </article>
      </section>
      <ul> <!--Lista desordenada: Sin numerar-->
        <li><!--Item List. Elementos de la lista--></li>
      </ul>
      <ol></ol> <!--Lista ordenada: Numerada-->
    </main>
    <footer> <!--Sección final de nuestro website-->
    </footer>
    <p>Soy un texto</p> <!--Párrafo, texto-->
    <h1>Soy un titulo</h1> 
    <!--Títulos, muestran el texto más grande y con negrilla. Existen desde el h1 al h6-->
    <a href="#">Soy un link</a>
    <!--Enlaces/links que nos permitirán movernos entre páginas.-->
  </body>
```
### Imagenes
PNG -> Sin perdida de calidad, la manera correcta de pedir es imagen png con transparentes LossLess
- GIF -> Formato fijo
- JPG, JPEG -> Formato con perdida Lossy
- SVG -> Sin perdida Vector/Lossless No pierda calidad por nada del mundo mundial.
![image](https://user-images.githubusercontent.com/65831379/168197006-8caf2305-e91b-47bf-a558-ae230d6df3cb.png)
Con esta informacion ya se puede trabajar con diseñadores entendiendo la calidad y la imagen adecuada para los istios web.

### Optimizacion de Imagenes
El peso ideal de una imagen para una web es de 100 a 70 kb, para esto es recomendable considerar las siguientes paginas:
1. Tiny PNG Esta pagina comprime las imagenes intentado no perder calidad
2. Verexif Esta elimina los metadatos que agregan un peso extra al final
Una pagina muy recomendable de imagenes gratis es:
- pexels.com
