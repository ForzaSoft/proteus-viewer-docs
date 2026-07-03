# Barra de Navegación

La barra de navegación (barra de vista previa de series) está ubicada en el lado izquierdo del visor y proporciona acceso rápido a todos los estudios, series e imágenes de la sesión actual. Muestra miniaturas y la información esencial para una navegación eficiente por los datos DICOM.

## Información del Paciente y del Estudio

En la parte superior de cada estudio en la barra de navegación encontrará:

- **Información del Paciente**: Nombre del paciente y fecha de nacimiento
- **Detalles del Estudio**: Fecha y hora del estudio, descripción del estudio
- **Modalidad**: La modalidad de imagen utilizada (TC, RM, Rayos X, etc.)
- **Número de Series**: Número total de series en el estudio

## Miniaturas de Series

Cada serie se representa mediante una imagen en miniatura que muestra:

- **Imagen de Vista Previa**: Una imagen representativa de la serie
- **Descripción de la Serie**: La descripción de la serie
- **Número de Imágenes**: Número total de imágenes en la serie (mostrado como "fotogramas")
- **Número de Serie**: El número de serie para su identificación

### Seleccionar una Serie

Haga clic en cualquier miniatura de serie para cargarla en la ventana activa.

## Key Objects (KO)

Cuando un estudio contiene Key Objects, cada grupo de Key Objects se muestra como una serie propia en la parte superior del estudio, por encima de las demás series. Además de la información habitual de una serie, una serie de Key Objects muestra:

- **Imagen de Vista Previa**: Una miniatura de su primera imagen clave
- **Descripción**: El nombre del grupo de Key Objects
- <RiKey2Fill /> **Icono de Llave**: Una llave con un color distinto por grupo
- **Número de Imágenes**: El número de imágenes clave del grupo
- **Círculo de Selección**: Cuando el guardado está habilitado, un círculo marca el grupo activo — aquel al que **Alternar KO** (**k**) añade imágenes. Haga clic en el círculo para activar un grupo.

Haga clic en una serie de Key Objects para cargar sus imágenes clave en la ventana activa, donde se pueden explorar como una serie normal. Cuando un estudio contiene imágenes clave, su primera serie de Key Objects se carga automáticamente en la primera ventana.
