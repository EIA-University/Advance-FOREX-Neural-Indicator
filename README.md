## MANUAL DE USUARIO

Los pasos para la ejecución del sistema son los siguientes:

#### 1. ACTIVAR LA DESCARGA AUTOMÁTICA DE INFORMACIÓN DE DIVISAS

El archivo MQL5 llamado ***GetData.MQL5***, deberá ser movido a la carpeta ***/Scripts***, propia del software Metatrader, esta se encuentra ubicada en la siguiente ubicación:

> C:\Users\Username\AppData\Roaming\MetaQuotes\Terminal\D0E8209F77C8CF37AD8BF550E51FF075\MQL5\Scripts

Una vez hecho esto, se procede a correr el script anteriormente mencionado desde el software MQL5, lo cual generará cada 12 horas *(este intervalo de tiempo puede ser modificado desde el mismo archivo)*  la información respectiva a la divisa seleccionada utilizando periodos de un minuto, esta será consolidada y guardada en un archivo CSV llamado ***Dataset*** en la carpeta Files, adyacente a la ubicación mencionada anteriormente.
