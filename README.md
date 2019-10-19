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
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/2-RunScript.png">
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/3-AcceptScript.png">
</p>

Listo, este script generará cada 12 horas *(este intervalo de tiempo puede ser modificado desde el mismo archivo)*  la información respectiva a la divisa seleccionada utilizando periodos de un minuto, esta será consolidada y guardada en un archivo CSV llamado ***Dataset*** en la carpeta  ***/Files***, adyacente a la ubicación mencionada anteriormente, como se muestra en la siguiente imagen.

<p align="center">
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/4-FinScript.png">
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/5-Files.png">
</p>

#### 2. EJECUCIÓN DEL MODELO

Una vez se crea el ***Dataset***, se procede a correr el modelo escrito en el lenguaje R, para este ejemplo, utilizaremos el software RStudio, entonces ejecutaremos los archivos ***Model.R*** y ***Functions.MQL5*** (para seguir la lógica del tutorial, estos archivos deben estar juntos en la misa carpeta), se debe configurar primero el directorio de trabajo de la siguiente forma.

<p align="center">
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/6-WorkingDirectory.png">
</p>

Una vez hecho esto, se procede a modificar el nombre de usuario en las variables seañaladas a continación.

<p align="center">
  <img src="https://raw.githubusercontent.com/EIA-University/Advance-FOREX-Neural-Indicator/master/imgs/7-Variables.png">
</p>

Finalmente, se ejecuta el modelo mediante el archivo ***Model.R*** y el botón ***Run***, como se muestra en la siguiente imagen.

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
