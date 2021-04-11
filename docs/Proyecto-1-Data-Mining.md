Proyecto 1 Data Mining
================
Diego Aguilar Dañobeitía
8/4/2021

## Cargar los datos

Lo primero que se tiene que hacer para iniciar el análisis de los datos
es cargar el archivo que los contiene, lo que se guardará en la variable
“data”:

``` r
setwd("D:/Documentos/Files & Stuff/U/Data Mining/Proyecto 1")

data <- read.csv("sanguchez.csv", sep = ";")

head(data)
```

    ##                                                               url
    ## 1          https://365sanguchez.com/abocado-cantina-buenos-aires/
    ## 2                   https://365sanguchez.com/alba-hotel-matanzas/
    ## 3   https://365sanguchez.com/albedrio-restaurant-santiago-centro/
    ## 4 https://365sanguchez.com/albedrio-restaurant-santiago-centro-2/
    ## 5              https://365sanguchez.com/aldea-nativa-providencia/
    ## 6            https://365sanguchez.com/aleman-experto-providencia/
    ##                 Local                                         Direccion  Precio
    ## 1     Abocado Cantina   C1125AAE, French 2316, C1125AAF CABA, Argentina $5.210.
    ## 2          Alba Hotel   Carlos Ibañez del Campo s/n – Matanzas, Navidad  $7.000
    ## 3 Albedrio Restaurant     Huérfanos 640, Santiago, Región Metropolitana  $7.290
    ## 4 Albedrío Restaurant Pasaje Huerfanos 640 edificio B local 5, Santiago  $8.690
    ## 5        Aldea Nativa  Tobalaba 1799, Providencia, Región Metropolitana  $4.900
    ## 6      Alemán Experto Av. Pedro de Valdivia 1683, Providencia, Santiago  $6.500
    ##                                                                                                                  Ingredientes
    ## 1                                               Suprema de pollo dulce, espinaca, crema ácida, repollo avinagrado y guacamole
    ## 2                     Carne mechada en reducción de vino tinto, champiñones salteados, cebolla caramelizada y queso derretido
    ## 3                          Mayonesa al olivo, champiñones salteados, jalapeños, queso Mozzarella, papas hilo y cebolla morada
    ## 4                          Queso Mozzarella, Rúcula, Champiñon portobello relleno de cheddar y luego apanado en panko y frito
    ## 5 Tofu asado no transgénico, palta, tomate, champiñones, mix de hojas verdes orgánicas,  mayonesa de zanahoria vegana casera,
    ## 6                           Hamburguesa, queso Cheddar, cebolla caramelizada, berros, pepinillos y salsa Jack Daniel’s Honey.
    ##   nota
    ## 1    3
    ## 2    3
    ## 3    4
    ## 4    4
    ## 5    4
    ## 6    3
    ##                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               texto
    ## 1                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Ojo acá! En la sanguchería “Abocado” (@AbocadoCantina) de Recoleta, más que un sándwich exquisito (que igual estaba bueno), descubrí una maravilla para copiar: acá el apanado, el frito del pollo, era dulce. Y bien crocante. Exquisito. Les juro que es el mejor apanado que he probado en mi vida. A esta suprema de pollo dulce, la acompañaban con espinaca (yo la hubiese puesto a la crema), crema ácida, repollo avinagrado y guacamole. Lamentablemente, la palta acá en Argentina no es como la chilena. Es más aguachenta. Y el pan, nuevamente sigue la línea que me ha tocado en este país, que no logra ser del nivel que tenemos en Chile. Pero insisto: ese batido hay que exportarlo. Estaba exquisito. Y sigo pensando en él.
    ## 2                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           Aprovechando que me escapé a Matanzas con @catabarra_ a canjear mi regalo de cumpleaños (clases de surf), quise probar algunos sanguchitos de la zona. Y como hace un año me quedé a alojar en @albahotelboutique y tuve una muy buena experiencia, hoy quise darle una oportunidad a su carta de comida. Y a pesar de que en general nos fue bastante mal (3 de los platos andaban muuuy bajos), mi sanguchito salvó muy bien. Y es que la mezcla de carne mechada en reducción de vino tinto, champiñones salteados, cebolla caramelizada en marraqueta (y le sumé queso derretido), es demasiado buena. No falla. Así que de 1 a 5, este se lleva 3 narices de chancho. Es decir, es un buen sándwich. Vaya a probarlo con confianza. Una marrquetita crujiente y de poca miga, una mechada muy suave y harto queso son sus puntas de lanzas. Sí, hay cosas por mejorar. Por ejemplo, las “mechas” de la carne como que se pegaban unas a otras, entonces a veces de un mordisco te llevabas casi toda la carne. O el caldo lo haría más intenso. Porque lo que chorreaba aquí eran los champiñones más que la carne. Pero apaña harto, además que estás comiendo EN la playa misma.
    ## 3                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            Sin duda, uno de los lugares que me ENCANTA visitar. Lejos la mejor hamburguesa que tienen es la Portobello (con un champiñón frito relleno de Cheddar y todo), pero como no estamos en temporada de hongos, no había ahora. Esa, sin duda, se lleva cinco narices. Hoy vine a @RestoAlbedrio con@MaxKbzon y nos dimos la torta comiendo. Él fue por un sándwich de prieta con manzana verde, papas hilo y mayo de ají verde. Yo, una burger “Picante”, con mayonesa al olivo, champiñones salteados, jalapeños, queso Mozzarella, papas hilo y cebolla morada. Solo les adelanto una cosa: tienen una salsa de reducción de cerveza con jugo de piña y azúcar rubia, que debiesen venderla en bidones!! Es EXQUISITA!
    ## 4                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    Con @nitanzorron fuimos a probar esta maravilla de @albedrio_resto. Anoten: hamburguesa casera, queso mozzarella, rúcula y champiñon portobello relleno de cheddar y luego apanado en panko y frito . Una maravilla! Es que los champiñones rellenos ya son atómicos… Pero ahora que vienen fritos, tienes un sabor estratosférico. La mejor idea del mundo. Es una verdura muy “carnosa” y rica, realzada por el queso y el apanado. El toque amargo de la rúcula viene bien, y la hamburguesa en sí, creo que es la más jugosa que he probado. Me recordó a la de Ciudad Vieja. Anda perfecta. El pan Brioche, bien dulce, y de miga consistente. No tan aireada. Mi único punto a mejorar es que sentí que era muy “aguado” (los champiñones tienen alto porcentaje de agua), por lo que me faltó malicia. Un picante, o una salsa de ajo… No sé. Algo que te vuele la cabeza. De hecho, Albedrío tiene dos salsas que creo que pondrían a esta hamburguesa en el top chileno: la de la casa, que es una reducción de cerveza, pulpa de piña y azúcar rubia, y una mayonesa con cilantro y ajo que es perfecta. Con @nitanzorron conversamos que agregando esa salsa, el sandwich sube de nivel a SS3. Muy buena. Vayan a ver nuestra visita a mi canal de YouTube (link en mi perfil) para todos los detalles y comenten si les tinca porque encuentro que es mega creativa y muuuuy rica.
    ## 5                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Ojo los vegetarianos!! Porque gracias a@genoveva_tenaillon (síganla si quieren ver unas recetas exquisitas pero saludables al mismo tiempo) que me pasó el dato, encontré el templo de los sándwiches vegetarianos y jugos naturales wenos wenos wenos. Es Aldea Nativa, en Tobalaba, y a pesar de que es 99% más probable que prefiera un sándwich carnívoro, creo que los que probé acá son de los mejorcitos que me han tocado (hasta ahora, en La Tegualda están los mejores). El Barros Luco de la Geno estaba bien bueno (con carne de libre pastoreo, sin hormonas ni antibióticos… Y no, claramente este no era veggie jaja), pero me gustó más el mío: tofu asado no transgénico, palta, tomate, champiñones, mix de hojas verdes orgánicas, y le sumé una mayonesa de zanahoria vegana casera, que viene con todos los sándwiches (échensela entera). A ver. Era rico, pero la nota se la lleva principalmente porque es el mejor tofu que he probado en Chile. En general lo cocinan muy fome, pero este estaba marinado en soya y asado a la plancha, así que tenía un gustito distinto al típico “quesillo sin sabor” jajaj. Además, venía como con un cevichito de champiñones que también se lo puse adentro  y agarró una jugosidad que el pan agradeció. Con estos dos ingredientes que le puse, las verduras agarraron un aliño exquisito. De los vegetarianos que he probado, es de los más ricos. Pero si no te gusta el Tofu, también puedes probar alguna de las hamburguesas vegetarianas que tienen. Me gustó harto el lugar, además de que también es un mercado donde venden miles de productos orgánicos, vegetarianos y de esa onda.
    ## 6 Salsa de bourbon: checkAlemán ExpertoCómo llegué a Alemán ExpertoYa había venido un par de veces al Alemán Experto. Tanto al local de Santa Magdalena, como a este de Pedro de Valdivia. En todas las visitas tuve suerte dispar. En algunos me gustó harto, otras no tanto.La cosa es que hoy tuve que hacer trámites cerca, y como tenía poco tiempo para buscar una sanguchería, preferí ir al Alemán Experto, que aún no lo sumaba a 365 Sánguchez.Fotos tomadas con mi celular Sony Xperia XRestaurante y sanguchería Alemán ExpertoAlemán Experto es una sanguchería que cuenta con dos locales. El primero está en Santa Magdalena, y el otro en Pedro de Valdivia, en la esquina con Francisco Bilbao. Ojo, que también están abriendo uno en La Dehesa.Este restaurante es, tal como lo dice su nombre, bien alemán. Es decir, abundan los sánguches grandes y la cerveza.Hablando del local de Pedro de Valdivia, siento que hicieron un gran trabajo con su fachada exterior. Si no me creen, miren la foto de más arriba. Y es que la terraza que sacaron está increíble. Además, por su ubicación, siempre hay gente, por lo que me tinca que se arma buen ambiente para los after office.Les dejo su pagina web. Carta de sándwiches Alemán ExpertoLa carta de sándwiches del Alemán Experto es amplia, tanto en sus bases, como también en sus combinaciones gourmet y clásicas.Por el lado más jugado, la sanguchería Alemán Experto cuenta con hamburguesas y mechadas BBQ. De las primeras, destacan una que tiene camarones y queso azul ($6.400), y la que pedí yo. Se llama Jack Daniel’s Honey, y tiene una salsa basada en ese licor, además de queso Cheddar, berros, cebolla caramelizada y pepinillos.En las mechadas BBQ, hay dos opciones. una con tocino crispy, y la otra con queso Azul y aros de cebolla.Luego de esta sección más “gourmet”, Alemán Experto también cuenta con hamburguesas, churrascos, lomitos, aves, salchichas y mechadas para poder armarlas como italianos, lucos y chacareros.Para terminar, hay una sección de sándwiches vegetarianos. Son hamburguesas de quinoa, y tiene cuatro combinaciones distintas. Hamburguesa Jack Daniel’s Honey en Alemán ExpertoA pesar de no ser un fanático del bourbon, admito que sí me gusta esta variante con toques de miel. Y en una salsa, mejor aún.Tengo que decir que es un sándwich correcto. La salsa no se roba el protagonismo, y aporta un toque justo de dulzor y también de “malicia”.La cebolla caramelizada estaba suave, y los berros perfectos para contrastar el frescor con lo dulce de la cebolla y la salsa.Lo que no me gustó tanto, es que la hamburguesa estaba un poco seca. Tuvo suerte, eso sí, de que venía acompañada con harta salsa, por lo que lograba pasar piola. Pero si nos quedamos en la carne, le falta.Y el otro punto negativo, y esto ya parece que es una maldición que me persigue, fue el queso Cheddar. Primero, porque no estaba derretido. Cueck. Y segundo, porque su sabor era demasiado plástico. Les prometo que tengo ganas de hacer una cata de quesos Cheddar, quizás con Daniel Greve, para poderles recomendar cuáles son buenos. Pero este, no.Maridaje con Cerveza Austral LagerEn resumen: Alemán Experto puede ser experto en otras cosas, pero no en hamburguesasRecién ahora, que estoy escribiendo estas líneas, me doy cuenta que quizás hice una movida tonta. Si voy a un lugar que se llama Alemán Experto, lo normal sería haber pedido un lomito. Con chucrut, con pepinillos… algo por ahí.Se supone que los alemanes también le pegan a las fricandelas, pero este no fue el caso. De hecho, la carne no era tan especiada como suele serlo en ese país. Pero aún así, me tinca que el lomito aquí puede ser un gran acierto.Quedé con ganas de volver. Volver y probar otra proteína, como el lomito o la mechada. Así que nos vemos pronto, Alemán Experto.

``` r
str(data)
```

    ## 'data.frame':    410 obs. of  7 variables:
    ##  $ url         : chr  "https://365sanguchez.com/abocado-cantina-buenos-aires/" "https://365sanguchez.com/alba-hotel-matanzas/" "https://365sanguchez.com/albedrio-restaurant-santiago-centro/" "https://365sanguchez.com/albedrio-restaurant-santiago-centro-2/" ...
    ##  $ Local       : chr  "Abocado Cantina" "Alba Hotel" "Albedrio Restaurant" "Albedrío Restaurant" ...
    ##  $ Direccion   : chr  "C1125AAE, French 2316, C1125AAF CABA, Argentina" "Carlos Ibañez del Campo s/n – Matanzas, Navidad" "Huérfanos 640, Santiago, Región Metropolitana" "Pasaje Huerfanos 640 edificio B local 5, Santiago" ...
    ##  $ Precio      : chr  "$5.210." " $7.000" "$7.290" "$8.690" ...
    ##  $ Ingredientes: chr  "Suprema de pollo dulce, espinaca, crema ácida, repollo avinagrado y guacamole" " Carne mechada en reducción de vino tinto, champiñones salteados, cebolla caramelizada y queso derretido" "Mayonesa al olivo, champiñones salteados, jalapeños, queso Mozzarella, papas hilo y cebolla morada" "Queso Mozzarella, Rúcula, Champiñon portobello relleno de cheddar y luego apanado en panko y frito" ...
    ##  $ nota        : int  3 3 4 4 4 3 3 3 3 3 ...
    ##  $ texto       : chr  "Ojo acá! En la sanguchería “Abocado” (@AbocadoCantina) de Recoleta, más que un sándwich exquisito (que igual es"| __truncated__ "Aprovechando que me escapé a Matanzas con @catabarra_ a canjear mi regalo de cumpleaños (clases de surf), quise"| __truncated__ "Sin duda, uno de los lugares que me ENCANTA visitar. Lejos la mejor hamburguesa que tienen es la Portobello (co"| __truncated__ "Con @nitanzorron fuimos a probar esta maravilla de @albedrio_resto. Anoten: hamburguesa casera, queso mozzarell"| __truncated__ ...

``` r
dim(data)
```

    ## [1] 410   7

Se puede observar que existen 410 entidades con 7 variables.

## Cargar las librerías

Luego, se procede a cargar las librerías necesarias:

``` r
library(tidyverse)
```

    ## Warning: package 'tidyverse' was built under R version 4.0.5

    ## -- Attaching packages --------------------------------------- tidyverse 1.3.0 --

    ## v ggplot2 3.3.3     v purrr   0.3.4
    ## v tibble  3.1.0     v dplyr   1.0.5
    ## v tidyr   1.1.3     v stringr 1.4.0
    ## v readr   1.4.0     v forcats 0.5.1

    ## Warning: package 'ggplot2' was built under R version 4.0.5

    ## Warning: package 'tibble' was built under R version 4.0.5

    ## Warning: package 'tidyr' was built under R version 4.0.5

    ## Warning: package 'readr' was built under R version 4.0.5

    ## Warning: package 'purrr' was built under R version 4.0.5

    ## Warning: package 'dplyr' was built under R version 4.0.5

    ## Warning: package 'stringr' was built under R version 4.0.5

    ## Warning: package 'forcats' was built under R version 4.0.5

    ## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(tidyr)

library(datastructures)
```

    ## Warning: package 'datastructures' was built under R version 4.0.5

    ## Loading required package: Rcpp

    ## 
    ## Attaching package: 'datastructures'

    ## The following object is masked from 'package:utils':
    ## 
    ##     stack

``` r
library(stringr)

library(janitor)
```

    ## Warning: package 'janitor' was built under R version 4.0.5

    ## 
    ## Attaching package: 'janitor'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     chisq.test, fisher.test

## Pre procesamiento de los datos

Se procede a limpiar los datos en base al objetivo: obtener una receta
de un sandwich y asegurar su buena calificación. Antes de pasar al
siguiente paso, se estima conveniente definir cómo se va a llevar a cabo
el pre procesamiento para este estudio en particular. Primero, se
reducirán los datos a las dimensiones necesarias para el experimento.
Luego, se eliminarán las entidades con valores faltantes y duplicadas.
Finalmente, se mantendrán las entidades cuyo valor en la variable “nota”
corresponda al máximo posible, a la vez que se separen cada uno de los
ingredientes en uno solo por columna. Esto se hace debido a que el mejor
indicador de la valoración de un ingrediente es cuando se considera su
presencia en conjunto con otros ingredientes, y si se tiene que, en
dicha combinación, tiene nota máxima, entonces ese ingrediente, junto a
los demás que cumplen con los mismos criterios, debe ser considerado
para la mejor receta, a diferencia de ingredientes presentes en
combinaciones con notas peores.

NOTA: Se pensó también en expandir la variable “Ingredientes” en varios
subtipos como: “Proteína”, “Aderezo” e “Ingredientes restantes”, pero el
análisis resultante de dicha expansión no sería muy correcto ya lo que
se podría hacer es correlacionar ingredientes individuales a una nota,
lo que no es representativo de cada sandwich en sí, y puede llevar a
combinaciones que no aseguren una buena calificación.

### Reducción de dimensionalidad

Como en este ejercicio se necesita conseguir, a partir de los datos, una
receta para asegurar una buena calificación de un sandwich, las únicas
variables importantes son las de “Ingredientes” y “nota”, por lo que se
procede a eliminar las restantes:

``` r
datared <- data[c("Ingredientes", "nota")]

dim(datared)
```

    ## [1] 410   2

Se observa que ahora se cuenta con los mismos 410 datos, pero ahora con
sólo 2 variables, que son las que se necesitan.

### Eliminación de entidades con valores faltantes

Luego se necesita limpiar las entidades que tienen valores faltantes
(NA) de los datos:

``` r
dataclean <- na.omit(datared)

dim(dataclean)
```

    ## [1] 402   2

Se observa que ahora existen 402 datos, ya que se eliminaron 8 con
valores faltantes.

### Eliminación de entidades duplicadas

Después se procede a eliminar entidades que poseen los mismos valores
para cada variable entre sí:

``` r
dataunique <- unique(dataclean)

dim(dataunique)
```

    ## [1] 402   2

Se observa que no disminuyó el número de entidades, por lo que no
existen entidades duplicadas.

### Selección de entidades en base a su nota

Luego, se van a seleccionar las entidades que tienen el valor máximo en
el atributo “nota”. Primero se procede a determinar el valor máximo que
toma esta variable

``` r
max(dataunique$nota, na.rm = TRUE)
```

    ## [1] 5

Se tiene que el valor máximo de la nota corresponde a 5. Luego, en base
a esto, se seleccionan las entidades que posean esta nota:

``` r
dataunique[2] <- lapply(dataunique[2], as.numeric)

datafilter <- dataunique %>% filter(nota == 5)

dim(datafilter)
```

    ## [1] 56  2

Se obtienen 56 entidades con valoración 5.

### Separiación de variable “Ingredientes” en ingredientes individuales

Finalmente, para esta fase de pre procesamiento de los datos, se va a
separar cada ingrediente contenido en la variable ingredientes y se van
a generar entidades separadas para cada uno de estos, conservando la
nota correspondiente al sandwich al que pertenecen. Además de esto, se
van a limpiar los datos que incluyen carácteres extra o información
irrelevante para este caso, junto a eliminar la variable “nota”.

``` r
datasep <- separate_rows(datafilter, Ingredientes, sep=",", convert = FALSE)
datasep3 <- separate_rows(datasep, Ingredientes, sep=" en ", convert = FALSE)
datasep4 <- separate_rows(datasep3, Ingredientes, sep=" con ", convert = FALSE)
datasep2 <- separate_rows(datasep4, Ingredientes, sep=" y ", convert = FALSE)

for (i in 1:dim(datasep2)[1]) {
  if (substr(datasep2[i, "Ingredientes"], 1, 1) == ' '){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 2, nchar(datasep2[i, "Ingredientes"]))
  }
  if (substr(datasep2[i, "Ingredientes"], 1, 3) == 'en '){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 4, nchar(datasep2[i, "Ingredientes"]))
  }
  if (substr(datasep2[i, "Ingredientes"], 1, 4) == 'con '){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 5, nchar(datasep2[i, "Ingredientes"]))
  }
  if (substr(datasep2[i, "Ingredientes"], 1, 18) == 'sobre una cama de '){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 19, nchar(datasep2[i, "Ingredientes"]))
  }
  if (substr(datasep2[i, "Ingredientes"], 1, 3) == 'un '){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 4, nchar(datasep2[i, "Ingredientes"]))
  }
  if (substr(datasep2[i, "Ingredientes"], 1, 9) == 'toque de '){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 10, nchar(datasep2[i, "Ingredientes"]))
  }
  if (substr(datasep2[i, "Ingredientes"], 1, 10) == 'exquisito '){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 11, nchar(datasep2[i, "Ingredientes"]))
  }
  if (substr(datasep2[i, "Ingredientes"], 1, 7) == 'montado'){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 8, nchar(datasep2[i, "Ingredientes"]))
  }
  if (substr(datasep2[i, "Ingredientes"], nchar(datasep2[i, "Ingredientes"]), nchar(datasep2[i, "Ingredientes"])) == ' '){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 1, nchar(datasep2[i, "Ingredientes"])-1)
  }
  if (substr(datasep2[i, "Ingredientes"], nchar(datasep2[i, "Ingredientes"]), nchar(datasep2[i, "Ingredientes"])) == '.'){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 1, nchar(datasep2[i, "Ingredientes"])-1)
  }
  if (substr(datasep2[i, "Ingredientes"], nchar(datasep2[i, "Ingredientes"])-15, nchar(datasep2[i, "Ingredientes"])) == ' hecha ahí mismo'){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 1, nchar(datasep2[i, "Ingredientes"])-16)
  }
  if (substr(datasep2[i, "Ingredientes"], nchar(datasep2[i, "Ingredientes"])-18, nchar(datasep2[i, "Ingredientes"])) == ' (340 grs de carne)'){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 1, nchar(datasep2[i, "Ingredientes"])-19)
  }
  if (substr(datasep2[i, "Ingredientes"], nchar(datasep2[i, "Ingredientes"])-6, nchar(datasep2[i, "Ingredientes"])) == ' casero'){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 1, nchar(datasep2[i, "Ingredientes"])-7)
  }
  if (substr(datasep2[i, "Ingredientes"], nchar(datasep2[i, "Ingredientes"])-8, nchar(datasep2[i, "Ingredientes"])) == ' cubierta'){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 1, nchar(datasep2[i, "Ingredientes"])-9)
  }
  if (substr(datasep2[i, "Ingredientes"], nchar(datasep2[i, "Ingredientes"])-18, nchar(datasep2[i, "Ingredientes"])) == '. Agregado mayonesa'){
    datasep2[i, "Ingredientes"] = str_sub(datasep2[i, "Ingredientes"], 1, nchar(datasep2[i, "Ingredientes"])-19)
  }
  datasep2[i, "Ingredientes"] <- tolower(datasep2[i, "Ingredientes"])
}

datasep2 <- datasep2[!(datasep2$Ingredientes == ""), ]

Ingredientes <- datasep2[c("Ingredientes")]

dim(Ingredientes)
```

    ## [1] 338   1

## Análisis de los datos

Ya que se han limpiado y ordenado los datos de forma correcta, se
procede al análisis de este para resolver la problemática planteada en
este caso. Para obtener una receta de sandwich que asegure una buena
calificación, se va a crear una tabla que represente el número de
ocurrencias de cada ingrediente, con frecuencia descendente, y se
calculará el promedio de ingredientes de todos los sandwiches. Con este
valor, se tomarán los primeros n-ésimos ingredientes y se tendrá el
“sandwich perfecto”. Cabe destacar que debe haber un ingrediente que sea
algún tipo de pan o similar, porque sin este no se tendrá un sandwich.
Si dentro de los primeros n-ésimos ingredientes no se encuentra ningún
ingrediente de este tipo, se tomarán los primeros n-1-ésimos
ingredientes y se buscará el ingrediente tipo pan con la mayor
frecuencia.

``` r
table1 <- (table(Ingredientes))

tablematrix <- as.data.frame(table1)

tablefinal <- tablematrix[order(-tablematrix$Freq),]

print(tablefinal)
```

    ##                                          Ingredientes Freq
    ## 217                                            tomate   15
    ## 90                                            lechuga   10
    ## 127                                             palta    8
    ## 34                                     cebolla morada    7
    ## 213                                            tocino    7
    ## 32                               cebolla caramelizada    5
    ## 149                                        pepinillos    5
    ## 188                                            rúcula    5
    ## 79                                        huevo frito    4
    ## 103                                          mayonesa    4
    ## 105                                   mayonesa casera    4
    ## 166                                     queso cheddar    4
    ## 177                                  queso mozzarella    4
    ## 14                                                ajo    3
    ## 70                                        hamburguesa    3
    ## 101                                        marraqueta    3
    ## 119                                     miel de maple    3
    ## 164                                             queso    3
    ## 165                                   queso americano    3
    ## 8                                                 ají    2
    ## 10                                  ají cherry pepper    2
    ## 11                                          ají verde    2
    ## 13                              ajíes verdes rellenos    2
    ## 19                           aros de cebolla apanados    2
    ## 22                                             berros    2
    ## 29                                      carne mechada    2
    ## 30                                            cebolla    2
    ## 48                                            chucrut    2
    ## 65                                           espinaca    2
    ## 112                                    mayonesa spicy    2
    ## 114                                           mechada    2
    ## 117                              mermelada de cebolla    2
    ## 123                                         mix verde    2
    ## 124                                           mostaza    2
    ## 125                                        mozzarella    2
    ## 130                                       pan brioche    2
    ## 143                                        papas hilo    2
    ## 153                                          pimentón    2
    ## 160                                    porotos verdes    2
    ## 167                                       queso crema    2
    ## 170                                    queso de cabra    2
    ## 199                                   salsa de tomate    2
    ## 203                                      salsa streat    2
    ## 210                                       sopaipillas    2
    ## 215                                   tocino crocante    2
    ## 216                                   tocino glaseado    2
    ## 219                                    tomates asados    2
    ## 223                                         zanahoria    2
    ## 1                                                 1/2    1
    ## 2                                          50% prieta    1
    ## 3                                       aceite de ajo    1
    ## 4                                    aceite de sésamo    1
    ## 5                                    aceitunas verdes    1
    ## 6                                aderezo de zanahoria    1
    ## 7                                    agregado chancho    1
    ## 9                                        ají amarillo    1
    ## 12                                  ajíes blanqueados    1
    ## 15                      albóndigas de quinoa crocante    1
    ## 16                                         alcaparras    1
    ## 17                                             alioli    1
    ## 18                                    aros de cebolla    1
    ## 20                                    base de lechuga    1
    ## 21                                         berenjenas    1
    ## 23                                          betarraga    1
    ## 24                                             blanca    1
    ## 25                                           braseado    1
    ## 26                                  brotes de alfalfa    1
    ## 27                                   camarones fritos    1
    ## 28                                              carne    1
    ## 31                                      cebolla asada    1
    ## 33                                    cebolla crunchy    1
    ## 35                                   cebolla rebosada    1
    ## 36                             cebollas caramelizadas    1
    ## 37                                    cebollita frita    1
    ## 38                           cebollitas caramelizadas    1
    ## 39                          cerdo molida condimentada    1
    ## 40                                        champiñones    1
    ## 41                            champiñones portobellos    1
    ## 42                              champiñones salteados    1
    ## 43                                        chimichurri    1
    ## 44                           chips de betarraga frita    1
    ## 45                                    chips de camote    1
    ## 46                                            chorizo    1
    ## 47                                  chorizo argentino    1
    ## 49                          chucrut de repollo morado    1
    ## 50                                   churrasco filete    1
    ## 51                               corazón de alcachofa    1
    ## 52  costillar de cerdo 100% orgánico de cocción lenta    1
    ## 53                       costillar de cerdo al merkén    1
    ## 54                  costillitas de vacuno desmenuzada    1
    ## 55                         crema ácida al ciboullette    1
    ## 56                                crema de queso azul    1
    ## 57                             crudo de res machacado    1
    ## 58                                              curry    1
    ## 59                                        desmenuzado    1
    ## 60                                  doble hamburguesa    1
    ## 61                                doble queso cheddar    1
    ## 62                                         encurtidos    1
    ## 63                                ensaladilla criolla    1
    ## 64                                           entrañas    1
    ## 66                                      filete de res    1
    ## 67                                  fonduta de quesos    1
    ## 68                                              frito    1
    ## 69                                          garbanzos    1
    ## 71                              hamburguesa 50% carne    1
    ## 72                   hamburguesa de 3 cortes de carne    1
    ## 73                    hamburguesa de arañita de wagyu    1
    ## 74                     hamburguesa de carne de vacuno    1
    ## 75              hamburguesa de champiñones portobello    1
    ## 76                      hamburguesa de porotos negros    1
    ## 77                               hamburguesa dry-aged    1
    ## 78                                       hojas verdes    1
    ## 80                                             hummus    1
    ## 81                                           jalapeño    1
    ## 82                                          jalapeños    1
    ## 83                                      jamón serrano    1
    ## 84                                           jengibre    1
    ## 85                                            juliana    1
    ## 86                                            ketchup    1
    ## 87                                            kétchup    1
    ## 88                         kiss my hass (palta frita)    1
    ## 89                                      leche de coco    1
    ## 91                                    lechuga costina    1
    ## 92                                          legumbres    1
    ## 93                                             lengua    1
    ## 94                                              limón    1
    ## 95                                      lomo de cerdo    1
    ## 96                                        lomo de res    1
    ## 97                                longaniza de jabalí    1
    ## 98                                        mantequilla    1
    ## 99                            mantequilla aromatizada    1
    ## 100                        manzana verde caramelizada    1
    ## 102                                   mayonera casada    1
    ## 104                                mayonesa al chilli    1
    ## 106                                   mayonesa de ajo    1
    ## 107                              mayonesa de cilantro    1
    ## 108                                mayonesa de eneldo    1
    ## 109                               mayonesa de la casa    1
    ## 110                                mayonesa de rábano    1
    ## 111                                 mayonesa habanero    1
    ## 113                                  mayonesa trufada    1
    ## 115            mejillas de res cocinadas por 12 horas    1
    ## 116                                            merkén    1
    ## 118                                              miel    1
    ## 120            milanesa de posta (apanada sin harina)    1
    ## 121                                mix de champiñones    1
    ## 122                                  mix punta paleta    1
    ## 126                                           orégano    1
    ## 128                                               pan    1
    ## 129                              pan amasado especial    1
    ## 131                                      pan ciabatta    1
    ## 132                              pan ciabatta peruano    1
    ## 133                                    pan de centeno    1
    ## 134                                      pan de leche    1
    ## 135                                 pan de masa madre    1
    ## 136                                      pan de queso    1
    ## 137                                      pan focaccia    1
    ## 138                        pan focaccia de masa madre    1
    ## 139                                       pan francés    1
    ## 140                                   pan potato roll    1
    ## 141                                   panceta ahumada    1
    ## 142                                             panko    1
    ## 144                               pastelera de choclo    1
    ## 145                                          pastrami    1
    ## 146                                              pato    1
    ## 147                                             pebre    1
    ## 148                                pebre de cochayuyo    1
    ## 150                                           perejil    1
    ## 151                                  pesto de la casa    1
    ## 152                                            piedra    1
    ## 154                              pimentón acaramelado    1
    ## 155                                   pimiento morrón    1
    ## 156                                  pimientos asados    1
    ## 157                                plateada de vacuno    1
    ## 158                                pollo deshilachado    1
    ## 159                                   pollo especiado    1
    ## 161                                           poutine    1
    ## 162                            pulled chicken ahumado    1
    ## 163                                       punta ganso    1
    ## 168                             queso crema derretido    1
    ## 169                            queso crema saborizado    1
    ## 171                            queso de huentelauquén    1
    ## 172                                queso grana padano    1
    ## 173                                     queso havarti    1
    ## 174                                 queso las águilas    1
    ## 175                                   queso mantecoso    1
    ## 176                         queso mantecoso derretido    1
    ## 178                                   queso parmesano    1
    ## 179                                 queso pepper jack    1
    ## 180                                   queso provolone    1
    ## 181                             raíz picante (rábano)    1
    ## 182                                     reineta frita    1
    ## 183                               relish de betarraga    1
    ## 184                                    relish de piña    1
    ## 185                     relleno de pollo a la plancha    1
    ## 186                                           ricotta    1
    ## 187                                      ricotta fría    1
    ## 189                                     sal al merkén    1
    ## 190                                            salmón    1
    ## 191                                             salsa    1
    ## 192                                      salsa al ajo    1
    ## 193                                 salsa al cilantro    1
    ## 194                                    salsa barbecue    1
    ## 195                                  salsa bbq casera    1
    ## 196                                 salsa de cilantro    1
    ## 197                                  salsa de la casa    1
    ## 198                               salsa de queso azul    1
    ## 200                           salsa de tomates casera    1
    ## 201                                 salsa la birrería    1
    ## 202                                     salsa secreta    1
    ## 204                                 salsa sweet chili    1
    ## 205                                    salsa teriyaki    1
    ## 206                                           servido    1
    ## 207                                    sésamo tostado    1
    ## 208                        sierra ahumada desmenuzada    1
    ## 209                                        sopaipilla    1
    ## 211                                              soya    1
    ## 212                                tiras de zanahoria    1
    ## 214                           tocino ahumado crocante    1
    ## 218                                     tomate fresco    1
    ## 220                     tomates confitados al orégano    1
    ## 221                              veganesa de cilantro    1
    ## 222                                           vinagre    1
    ## 224                                  zapallo italiano    1
    ## 225                          zapallo italiano apanado    1
    ## 226                         zapallo japonés rostizado    1
    ## 227                                        zesty slaw    1
    ## 228                                 zucchini grillado    1

``` r
promedio1 = dim(Ingredientes)/dim(datafilter)

promedio2 = promedio1[1]

promediofinal = round(promedio2)

print(promediofinal)
```

    ## [1] 6

## Conclusión

Según los análisis anteriores, se llega a la conclusión de que el
sandwich que no solamente podría asegurar una buena calificación, sino
que la mejor de todas, sería un sandwich de 6 ingredientes (contando el
pan): tomate, lechuga, palta, cebolla morada y tocino, en pan
marraqueta.
