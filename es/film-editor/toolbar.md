# Barra de Herramientas

La barra de herramientas proporciona acceso rápido a las herramientas de diseño, edición e impresión del Editor de Película.

## Diseño

- <RiGridFill /> **Plantillas**: Abre el selector de plantillas para elegir un diseño para la película. Hay disponible una lista de plantillas configurables, cada una define el número y la disposición de las celdas de imagen en la página.

## Modo de Ratón

- <BiSquareRounded /> **Selección**: Cambia al modo Selección, permitiendo hacer clic e interactuar con celdas de imagen individuales.

- <RiContrastFill /> **Ventana de Imagen**: Cambia al modo Ventana/Nivel, permitiendo ajustar el brillo y el contraste de la imagen seleccionada.

- <RiDragMove2Fill /> **Mover**: Cambia al modo Mover, permitiendo reposicionar la imagen dentro de una celda.

- <RiZoomInLine /> **Zoom**: Cambia al modo Zoom, permitiendo ajustar el nivel de ampliación de la imagen seleccionada.

- <RiDeleteBinLine /> **Eliminar**: Cambia al modo Eliminar. Al hacer clic en una celda de imagen se elimina su contenido.

## Otras Herramientas

- <RiArrowGoBackFill /> **Restablecer**: Restablece la celda de imagen seleccionada a su estado inicial (zoom, desplazamiento, ventana/nivel).

- <RiAnticlockwiseLine /> **Rotar**: Alterna la orientación de la película entre Vertical y Horizontal. La orientación actual se muestra en la etiqueta de estado en la parte superior derecha de la barra de herramientas.

- <BiCog /> **Impresoras**: Abre el selector de impresoras. Hay dos grupos disponibles según la configuración:
  - **PDF**: Tamaños de papel del navegador (A4, A3).
  - **DICOM**: Impresoras DICOM configuradas.

- <RiSave2Fill /> **Guardar** *(si el guardado está habilitado)*: Guarda la película actual en el PACS.

- <RiFilePdf2Fill /> **PDF** *(solo impresora PDF)*: Genera y descarga la película como archivo PDF.

- <RiPrinterFill /> **Imprimir**: Envía la película a la impresora seleccionada.
