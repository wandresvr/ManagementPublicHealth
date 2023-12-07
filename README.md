![image](https://github.com/wandresvr/ManagementPublicHealth/assets/26063331/92b1acd7-2734-4ee6-a6d8-5ad6ba11fabd)



# Español:

## Gestión de salud pública.

El proceso de gestión de salud pública tiene los siguientes objetivos:

1. Dentro del proceso. la infomación de madres adolescentes, su adecuada prevención y gestión es clave en el desarrollo de la estrategia que se tiene actualmente. Es por lo cúal se descarga el informe “proporción madres adolescentes” todos los meses desde la página web, está página web tiene varias tablas en HTML, se usa el archivo ``TableLayout.xml`` en la ruta ``Data\Temp``.

2. Se descargan los archivos de resoluciones desde la página del ministerio de salud colombiano, para este caso se usa el parametro "DownloadNumsOfRes" dentro del archivo de parametros ``Config.xlsx``

3. Se descarga los archivos de lineamientos contenidos en las variables "DownloadGuidelinesScope" y "DownloadGuidelinesLead" desde la página del ministerio de salud de colombia.

4. Para los lineamientos dentro de la variable "DownloadGuidelinesScope" se extrae la información contenida en los archivos linemaientos descargados, pero solo la parte llamada "Alcance"; lo mismo ocurre para los lineamientos en "DownloadGuidelinesLead" pero en este se extrae la parte llamada "Lideres".

5. La información extraída se guarda en un documento de word, respectivamente.


## Arquitectura:

1. La arquitectura está definida de la siguiente manera:

Main
- Init
  - Init settings
  - Init apps
  - Kill apps
- Process
  - Get Data from teenage mothers
  - Get resolutions
  - Guidelines Scope
    - Get info
    - Extract into
    - Save info
  - Guidelines Lead
    - Get info
    - Extract into
    - Save info

2. Ademas de eso se tiene manejadores de errores globales de tipo:

 ### Init:
- Try:
    - Init
- Catch:
   - "end workflow"

### Process
- Try:
  - Process
- Catch:
  - Take a screenshot
  - Send email

3. Adicional a esto, para cada paso de "Process" existe un manejador de errores con la instrucción de continuar el siguiente paso.

## Ejecución:
Solo basta con ejecutar ``main.xaml`` en [UiPath Studio](https://www.uipath.com/developers/studio-download?_gl=1*771jmr*_gcl_au*MTU0Nzg4NjU1Ni4xNzAxODM3MDM5).
