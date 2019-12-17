# Análisis espacial de factores asociados al crimen y la vulnerabilidad social en Boston


## Resumen

Este repositorio contiene el código y datos de la presentación sobre el proyecto final del curso SP-1649 Tópicos de Estadística Espacial Aplicada: **Análisis espacial de factores asociados al crimen y la vulnerabilidad social en Boston**, desarrollado por Miguel Coto y Esteban Vargas, como parte de la Maestría en Estadística de la Universidad de Costa Rica. 

- [Análisis espacial de pobreza en Boston](#Crimenes-en-Boston-por-area)
  - [Resumen](#resumen)
  - [Estructura del repositorio](#estructura-del-repositorio)
  - [Datos](#datos)
    - [Fuentes de información](#fuentes-de-informaci%C3%B3n)
    - [Descripción del conjuntos de datos](#descripci%C3%B3n-de-los-conjuntos-de-datos)
    - [Variables en el conjunto de datos](#variables-en-cada-conjunto-de-datos)
  - [Procesamiento y análisis de los datos](#procesamiento-y-an%C3%A1lisis-de-los-datos)
    - [Análisis](#an%C3%A1lisis)
  - [Autores](#preguntas)
  - [Licencia](#licencia)

## Estructura del repositorio

El repositorio está compuesto por un archivo de Rmd (R markdown), usado para la limpieza y análisis de los datos, el documento final a entregar en Word, la presentación final en Powerpoint, y una carpeta que contienen los datos usados en el artículo final:

- El archivos de R, disponibles en formato `.Rmd`, contienen los procedimientos usados para la limpieza de los datos y para replicar los resultados y el análisis presentados en el informe final y la presentación (`proyecto4.R`).
- El archivo Word contiene el informe final (`Proyecto 4 - Miguel y Esteban.docx`)
- El archivo PowerPoint con la presentacion final (`Ppresentacion.pptx`)
- El video con la presentacion final (``)
- La carpeta `datos` contiene los datos usados en el artículo. 

## Datos

### Fuentes de información

Los datos usados en el análisis y contenidos en la carpeta `datos` provienen de:

- [Datos de vulnerabilidad social (Boston Maps)](http://bostonopendata-boston.opendata.arcgis.com/datasets/34f2c48b670d4b43a617b1540f20efe3_0)
- [Datos de crimenes (Boston Maps)](https://data.boston.gov/dataset/crime-incident-reports-august-2015-to-date-source-new-system)


### Descripción del conjuntos de datos

Los datos se basan en un marco para comprender la relación entre los factores sociales que reducen la resiliencia en las ciudades para la ciudad de Boston publicado en 2015. La vulnerabilidad social se define como la susceptibilidad desproporcionada de algunos grupos sociales a los impactos de los peligros, incluida la muerte, las lesiones, la pérdida o la interrupción de los medios de vida. 
Con base en esto se toman variables como la cantidad adultos mayores, niños, personas de color, personas con dominio limitado del inglés, personas con discapacidades, personas con enfermedades y el número de personas con bajos ingresos o sin ingresos para pronosticar el número de crimenes por distrito.

### Variables en el conjunto de datos

1) `boston.sph`:

   - **name:** nombre del barrio en Boston.
    - **crimes:** número total de crimenes.
    - **Low_to_No:** personas con ingreso bajo o nulo. Los datos representan un campo calculado que combina personas que estaban 100% por debajo del nivel de pobreza y aquellas que estaban entre 100 y 149% del nivel de pobreza.
   - **TotDis:** personas con discapacidad. Población total, que incluye: dificultad auditiva, dificultad para la visión, dificultad cognitiva, dificultad ambulatoria, dificultad para el autocuidado y dificultad para vivir de forma independiente.
   - **TotChild:** Cantidad de niños. Población menor a 5 años.
   - **OlderAdult:** Cantidad de adultos mayores. Población mayor a 65 años.
   - **LEP:** Dominio limitado de inglés. Población con manejo limitado de inglés.
   - **POC2:** Cantidad de población de color. Hispanos, negros, nativos americanos, asiáticos, isleños, hispanos no blancos..
   - **MedIllnes:** Cantidad de personas con enfermedades. La enfermedad médica es la suma de asma en niños, asma en adultos, enfermedad cardíaca, enfisema, bronquitis, cáncer, diabetes, enfermedad renal y enfermedad hepática.
  

## Procesamiento y análisis de los datos

Los datos fueron procesados usando R. Se realizó una exploración y limpieza de los datos pues habían barrios de la ciudad de Boston que eran pequeñas islas alejadas de la gran mayoría de territorio continental lo que resultaba en agrupaciones espurias. Teniendo este conjunto de datos en el formato deseado, se realizaron distintos análisis de los datos en R, descritos más a profunidad en el script respectivo y el artículo, que producen, entre otros, los resultados disponibles en el archivo `proyecto4.Rmd`.


### Análisis

Se tomaron diferentes variables asociadas al fenómeno de vulnerabilidad social en Boston, para a partir de ellas, modelar de forma espacial el nivel de criminalidad en la zona. Mediante la prueba de Moran, se obtuvo evidencia de autocorrelación espacial lo cual permitió evaluar distintos modelos, de los cuales el Durbin fue que realizó un mejor ajuste. Las variables de cantidad de población de color y cantidad de personas con enfermedades médicas fueron las de mayor aporte al modelaje espacial.

## Autores

- Miguel Coto: cott527@gmail.com
- Esteban Vargas: esvapa8@gmail.com

## Licencia

El código usado y presentado en este repositorio tiene una licencia [MIT](https://opensource.org/licenses/MIT), mientras que los datos y figuras tienen una licencia [CC-BY](https://creativecommons.org/licenses/by/4.0/deed.es), a menos que se especifique explicitamente otra licencia. Las condiciones de las licencias anteriormente mencionadas están descritas en el archivo `LICENSE` de este repositorio.

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Licencia Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />Esta obra está bajo una <a rel="license" href="http://creativecommons.org/licenses/by/4.0/deed.es">Licencia Creative Commons Atribución 4.0 Internacional</a>.
