## MANUAL DE USUARIO

Los pasos para la ejecución del sistema son los siguientes:

#### 1. ACTIVAR LA DESCARGA AUTOMÁTICA DE INFORMACIÓN DE DIVISAS

El archivo MQL5 llamado ***GetData.MQL5***, deberá ser movido a la carpeta ***/Scripts***, propia del software Metatrader, esta se encuentra ubicada en la siguiente ubicación:

> C:\Users\Username\AppData\Roaming\MetaQuotes\Terminal\D0E8209F77C8CF37AD8BF550E51FF075\MQL5\Scripts

El resultado será algo así:

<p align="center">
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/1-ScriptsFolder.png">
</p>

Una vez hecho esto, se procede a correr el script anteriormente mencionado desde el software MQL5, dando click en el botón verde señalado en la imagen, luego aparacerá una ventana de confirmación en la cual solo se da click en aceptar.

<p align="center">
  <img src="https://i.gyazo.com/76d7fcbd22c3e1d27f6b690b96b6f4b7.gif" alt="Image from Gyazo" width="800"/>
</p>

Listo, este script generará cada 12 horas *(este intervalo de tiempo puede ser modificado desde el mismo archivo)*  la información respectiva a la divisa seleccionada utilizando periodos de un minuto, ésta será consolidada y guardada en un archivo CSV llamado ***Dataset*** en la carpeta  ***/Files***, adyacente a la ubicación mencionada anteriormente, como se muestra en la siguiente imagen.

<p align="center">
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/4-FinScript.png">
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/5-Files.png">
</p>

#### 2. EJECUCIÓN DEL MODELO

Una vez se crea el ***Dataset***, se procede a correr el modelo escrito en el lenguaje R, para este ejemplo, utilizaremos el software RStudio, entonces ejecutaremos los archivos ***Model.R*** y ***Functions.MQL5*** (para seguir la lógica del tutorial, estos archivos deben estar juntos en la misa carpeta), se debe configurar primero el directorio de trabajo de la siguiente forma.

<p align="center">
<img src="https://i.gyazo.com/ba84fcb1a5a584c91b538b90f9ed69c8.gif" alt="Image from Gyazo" width="546"/>
</p>

Una vez hecho esto, se procede a modificar el nombre de usuario en las variables señaladas a continación (dentro del archivo ***Model.R***).

<p align="center">
  <img src="https://i.gyazo.com/51601737afca1fcab8ddfbe9fe023cc9.gif" alt="Image from Gyazo" width="688"/>
</p>

Finalmente, se ejecuta el modelo mediante el archivo ***Model.R*** y el botón ***Run*** (después de seleccionar todo el código), como se muestra en la siguiente imagen.

<p align="center">
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/8-RunModel.png">
</p>

El resultado sera lo siguiente:

En consola se puede observar el índice de correlación y el error cuadrático total.

<p align="center">
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/9-Console.png">
</p>

Además de las creación de dos archivos: ***GeneticValues.CSV***, con los valores de los pesos de los retardos y ***ModelValues.CSV***, con los valores de W, C y el alfa.

<p align="center">
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/10-GeneticValues.png">
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/11-ModelValues.png">
</p>

#### 3. EJECUCIÓN DEL ADVANCE INDICATOR

Para utilizar el Advance Neural Indicator, es necesario mover el archivo ***AdvanceNeuralIndicator.mq5*** a la carpeta de indicadores de METATRADER 5.0, la cual se encuentra en la siguiente ruta:

> C:\Users\Username\AppData\Roaming\MetaQuotes\Terminal\D0E8209F77C8CF37AD8BF550E51FF075\MQL5\Indicators


El resultado será algo así:

<p align="center">
  <img src="https://i.gyazo.com/17fa3c9ab59e030ccd0f58a2ca286fc7.png">
</p>

Posteriormente al abrir MetaEditor el indicador estará disponible en la carpeta de indicadores.

<p align="center">
  <img src="https://i.gyazo.com/413c155d0d572f946c48f40317b44dd3.png">
</p>

En la sección de definición de variables será posible configurar, entre otros parámetros del modelo, el número de retardos a tener en cuenta para las estimaciones **delays** y el número de neuronas ocultas **hiddenNeurons**

<p align="center">
  <img src="https://i.gyazo.com/7d33627ae6ce4e6646f258e3d2c8e155.png">
</p>
