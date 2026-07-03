# Key Objects (Imágenes Seleccionadas)

Los Key Objects (KO) son una función estándar de DICOM que permite marcar y guardar imágenes o fotogramas significativos para su revisión posterior. Estas imágenes seleccionadas ayudan a identificar y navegar rápidamente hasta los hallazgos más importantes de un estudio.

## ¿Qué son los Key Objects?

Los Key Objects son marcadores especiales que resaltan imágenes importantes dentro de un estudio DICOM. Cuando se marca una imagen como Key Object, pasa a formar parte de un grupo con nombre al que se puede acceder fácilmente más adelante. Esto es especialmente útil para:

- Crear una colección de imágenes para informes
- Marcar imágenes para comparación o seguimiento
- Organizar imágenes para presentaciones o consultas

## Creación de Grupos de Key Objects

Puede crear uno o más grupos de Key Objects dentro de un estudio. Cada grupo tiene un nombre único y puede contener imágenes de diferentes series dentro del mismo estudio.

### Para Marcar una Imagen como Key Object:

1. Navegue hasta la imagen que desea marcar
2. Haga clic en el botón <RiKey2Fill /> **Alternar KO** en la barra de herramientas, o use su menú desplegable y seleccione **Alternar KO con Ventana** para preservar la configuración de ventana actual
3. Introduzca un título para su grupo de Key Objects (o seleccione un grupo existente)
4. La imagen quedará marcada con un indicador visual

### Múltiples Grupos

Puede organizar las imágenes seleccionadas en múltiples grupos, cada uno con su propio nombre descriptivo. Por ejemplo:
- "Hallazgos Principales"
- "Pretratamiento"
- "Comparación de Seguimiento"
- "Anomalías"

Cada grupo puede contener imágenes de diferentes series dentro del estudio, facilitando la recopilación de hallazgos relacionados en múltiples secuencias de imagen.

## Gestión de Key Objects

### Edición de Key Objects

Haga clic en el botón <RiEditFill /> **Edición KO** en la barra de herramientas para abrir el editor de Key Objects. En este editor puede:

- Crear nuevos grupos de Key Objects
- Renombrar grupos existentes
- Añadir o eliminar imágenes de los grupos
- Eliminar grupos completos
- Organizar sus selecciones

### Navegación entre Key Objects

Una vez marcadas las imágenes como Key Objects, puede navegar rápidamente entre ellas usando el menú desplegable de <RiEditFill /> **Edición KO**:

- **Saltar KO atrás**: Navega al Key Object anterior del grupo actual
- **Saltar KO adelante**: Navega al Key Object siguiente del grupo actual

### Guardar Key Objects

Tras crear o modificar sus selecciones de Key Objects, haga clic en el botón <RiSave2Fill /> **Guardar KOs** para guardar los cambios. Los Key Objects se almacenan como archivos DICOM con la modalidad KO.

## Visualización de Key Objects

### En la Barra de Navegación

Cuando hay Key Objects presentes en un estudio, cada grupo de Key Objects aparece como una serie propia en la parte superior de la barra de navegación, mostrando una miniatura de su primera imagen clave, el nombre del grupo, el número de imágenes clave y un icono de llave <RiKey2Fill /> de color. Un círculo de selección marca el grupo activo — aquel al que **Alternar KO** añade imágenes; haga clic en el círculo para cambiar de grupo.

Haga clic en una serie de Key Objects para cargar sus imágenes clave en la ventana activa, donde se pueden explorar como una serie normal. Para gestionar las selecciones, use el botón <RiEditFill /> **Edición KO** de la barra de herramientas.

### Indicadores Visuales

Las imágenes que forman parte de una selección de Key Objects están marcadas con indicadores visuales tanto en la ventana de imagen como en las miniaturas de la barra de navegación, lo que facilita su identificación a simple vista.

### Exportar al Editor de Película

Puede enviar fácilmente todas las imágenes de un grupo de Key Objects al Editor de Película para imprimirlas o guardarlas. Haga clic en el botón <RiCameraLine /> **Editor de Película** en la barra de herramientas y seleccione **Imágenes KO**.

## Flujo de Trabajo con Key Objects

Un flujo de trabajo típico para usar Key Objects:

1. **Revisar el estudio** e identificar las imágenes importantes

2. **Marcar imágenes** usando el botón <RiKey2Fill /> **Alternar KO** (o **Alternar KO con Ventana** desde su menú desplegable)

3. **Organizar** las imágenes en grupos con nombre usando el editor <RiEditFill /> Edición KO

4. **Navegar** entre las imágenes seleccionadas usando los botones Saltar KO Atrás/Adelante

5. **Guardar** las selecciones con el botón <RiSave2Fill /> Guardar KOs

6. **Revisar** los Key Objects seleccionando grupos desde la barra de navegación
