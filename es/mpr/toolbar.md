# Barra de Herramientas

La barra de herramientas proporciona acceso rápido a las herramientas de diseño, visualización y manipulación de imágenes en el modo MPR.

## Pantalla

- <RiGridFill /> **Cuadrícula**: Ajusta el diseño de ventanas. Configuraciones disponibles:
  - 2 Columnas [2|1], 2 Columnas [1|2], 3 Columnas
  - 2 Filas [2|1], 2 Filas [1|2], 3 Filas

- <RiInformationLine /> **Información de Pantalla**: Activa o desactiva la visualización de anotaciones DICOM. Su menú desplegable ofrece opciones adicionales:
  - **Mostrar Anotaciones**: Muestra u oculta el texto DICOM superpuesto en las imágenes.
  - **Mostrar Medidas**: Muestra u oculta las anotaciones de medición.

## Modo de Ratón

- <RiStackFill /> **Explorar Serie**: Cambia al modo Serie, permitiendo navegar por los cortes.

- <RiContrastFill /> **Ventana de Imagen**: Cambia al modo Ventana/Nivel, permitiendo ajustar el brillo y el contraste.

- <RiDragMove2Fill /> **Mover**: Cambia al modo Mover, permitiendo reposicionar la imagen dentro de la ventana activa.

- <RiZoomInLine /> **Zoom**: Cambia al modo Zoom, permitiendo ajustar el nivel de ampliación.

- <RiRulerFill /> **Medidas**: Cambia al modo Medidas, proporcionando herramientas de medición. Consulte la [Barra de Herramientas del Visor](../viewer/toolbar.md) para ver la lista completa de herramientas disponibles.

## Otras Herramientas

- <RiArrowGoBackFill /> **Restablecer**: Restablece la ventana activa a su estado inicial (zoom, desplazamiento, ventana/nivel).

- <RiExpandHeightFill /> **Modo de Renderizado**: Establece el modo de proyección para la ventana activa. Su menú desplegable ofrece las siguientes opciones:
  - **MPR**: Reconstrucción multiplanar estándar.
  - **MIP**: Proyección de Intensidad Máxima — resalta los vóxeles de mayor valor a lo largo de cada rayo.
  - **MinIP**: Proyección de Intensidad Mínima — resalta los vóxeles de menor valor a lo largo de cada rayo.
  - **Avg**: Proyección de Intensidad Media — promedia todos los valores de vóxel a lo largo de cada rayo.

## Ayuda

- **Ayuda**: Abre el panel de Ayuda. Su menú desplegable también ofrece acceso a la referencia de **Atajos** de teclado del modo MPR.
