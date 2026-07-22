# Barra de Herramientas

La barra de herramientas proporciona acceso rápido a diversas herramientas y funciones para manipular y analizar imágenes DICOM.

## Configuración y Estudio

- <RiFolderOpenLine /> **Abrir**: Abre archivos DICOM locales. Su menú ofrece:
  - **Abrir Archivo...**: Abre uno o más archivos DICOM desde su equipo.
  - **Abrir Carpeta...**: Abre una carpeta completa y carga todos los archivos DICOM que contiene.

- <RiDatabase2Fill /> **Búsqueda de Estudio**: Abre el diálogo de búsqueda de estudios para cargar estudios adicionales desde el PACS.

- <BiCog /> **Configuración**: Abre la configuración de la aplicación para configurar fuentes DICOM, impresoras y preferencias del visor.

## Pantalla

- <RiGridFill /> **Cuadrícula**: Ajusta el diseño de ventanas para mostrar múltiples series simultáneamente. Admite configuraciones de hasta un máximo de 16 ventanas. Su menú desplegable ofrece opciones adicionales:
  - **Cuadrícula**: Vuelve a abrir el selector de diseño de cuadrícula.
  - **Dividir Series**: Distribuye las series del grupo activo entre las ventanas disponibles.
  - **Grupo de Series**: Submenú para seleccionar qué grupo de series se muestra.
  - **Cerrar Todas las Ventanas**: Vacía todas las ventanas y vuelve al diseño de una sola ventana.
  - **Cuadrículas predefinidas**: Una lista de diseños de cuadrícula fijos configurables.
  - **Modo Pantalla Completa**: Activa o desactiva la pantalla completa (**F11**).

- <RiLinkM /> **Modo de Sincronización**: La función de sincronización permite aplicar la misma configuración (posición de corte, zoom y desplazamiento, ventana) a las series de imágenes abiertas en múltiples paneles.

  Hay tres modos de sincronización disponibles:
  - <RiLinkMAuto /> **Auto**: Sincroniza automáticamente la configuración en todos los paneles
  - <RiLinkMManual /> **Manual**: Requiere activación manual para sincronizar la configuración
  - <RiLinkUnlinkM /> **Desactivado**: La sincronización está desactivada

  Su menú desplegable también ofrece opciones para controlar qué se sincroniza:
  - **Sincronizar Posición de Corte**: Sincroniza la posición de corte entre paneles
  - **Sincronizar Zoom y Desplazamiento**: Sincroniza la configuración de zoom y desplazamiento entre paneles
  - **Sincronizar Ventana**: Sincroniza la configuración de ventana/nivel entre paneles (desactivado por defecto)

- <RiInformationLine /> **Información de Pantalla**: Activa o desactiva la visualización de anotaciones DICOM. Su menú desplegable ofrece opciones adicionales:
  - **Mostrar Anotaciones**: Muestra u oculta la información de texto DICOM en las imágenes
  - **Mostrar Superposición DICOM**: Muestra u oculta los datos de superposición DICOM
  - **Mostrar Medidas**: Muestra u oculta las anotaciones de medición
  - **Mostrar Etiquetas DICOM**: Abre el visor de etiquetas DICOM para la imagen actual
  - **Fuentes DICOM**: Abre el diálogo de configuración de fuentes DICOM

## Modo de Ratón

- <RiStackFill /> **Explorar Serie**: Cambia al modo Serie, permitiendo navegar por las imágenes de la serie. Su menú desplegable ofrece acciones de navegación adicionales:
  - **Imagen Anterior**: Ir a la imagen anterior de la serie.
  - **Imagen Siguiente**: Ir a la imagen siguiente de la serie.
  - **Saltar Imágenes Atrás**: Saltar varias imágenes hacia atrás.
  - **Saltar Imágenes Adelante**: Saltar varias imágenes hacia adelante.

- <RiContrastFill /> **Ventana de Imagen**: Cambia al modo Ventana/Nivel, permitiendo ajustar los parámetros de Ventana y Nivel para optimizar la visibilidad de densidades de tejido específicas. Su menú desplegable ofrece opciones de ventana predefinidas:
  - **Ventana Predeterminada**: Restaura la ventana/nivel predeterminada de la serie.
  - **Dinámica Completa**: Aplica el rango dinámico completo de la imagen.
  - **Ventanas predefinidas**: Lista de ventanas fijas configurables (p. ej. Tejido Blando, Pulmón, Hueso para TC).
  - **Negativo**: Invierte la imagen (modo negativo).

- <RiDragMove2Fill /> **Mover**: Cambia al modo Mover, permitiendo reposicionar la imagen dentro de la ventana activa para ajustar el área de visualización.

- <RiZoomInLine /> **Zoom**: Cambia al modo Zoom, permitiendo ajustar el nivel de ampliación para agrandar o reducir la imagen. Su menú desplegable ofrece opciones de zoom predefinidas:
  - **Ajustar a Ventana**: Escala la imagen para llenar toda la ventana.
  - **Niveles de zoom predefinidos**: Lista de niveles de zoom fijos configurables.

- <RiRulerFill /> **Medidas**: Cambia al modo Medidas, proporcionando herramientas de medición. El icono refleja la última herramienta seleccionada:
  - <RiRulerFill /> **Longitud**: Mide la distancia entre dos puntos.
  - <BiCircle /> **Elipse**: Mide el área de una elipse y calcula el volumen ROI.
  - <TbAngle /> **Ángulo**: Mide el ángulo entre dos líneas.
  - <TbAngle /> **Ángulo de Cobb**: Mide el ángulo de Cobb entre dos líneas.
  - <RiArrowRightDownLine /> **Flecha**: Coloca una anotación de flecha direccional.
  - <RiText /> **Texto**: Coloca una anotación de texto libre.
  - <TbPolygon /> **Polígono**: Dibuja un polígono y mide su área.
  - <RiCrosshair2Line /> **Cruz**: Coloca una anotación de cruz.
  - <RiDeleteBin7Fill /> **Eliminar**: Elimina la medida seleccionada.
  - <RiDeleteBin7Fill /> **Eliminar Todo**: Elimina todas las medidas en la ventana actual.

## Otras Herramientas

- <RiArrowGoBackFill /> **Restablecer**: Restablece la serie a su estado inicial (zoom, desplazamiento, ventana/nivel).

- <MdRotate90DegreesCcw /> **Transformaciones**: El botón principal rota la imagen 90° en sentido antihorario. Su menú desplegable ofrece:
  - **Rotar 90° Antihorario**: Rota la imagen 90° en sentido antihorario (**ctrl + [**).
  - **Rotar 90° Horario**: Rota la imagen 90° en sentido horario (**ctrl + ]**).
  - **Voltear Horizontal**: Voltea la imagen horizontalmente (**ctrl + shift + [**).
  - **Voltear Vertical**: Voltea la imagen verticalmente (**ctrl + shift + ]**).

- <BiCameraMovie /> **Reproducir/Detener**: Activa o desactiva la reproducción de la secuencia de imágenes (modo Cine). Puede acelerar la reproducción con la tecla **flecha arriba + alt** y reducirla con **flecha abajo + alt**. Pulse la **barra espaciadora** para alternar entre reproducir y pausar.

## Avanzado

- <RiBox3Fill /> **MPR**: Abre la vista de Reconstrucción Multiplanar. Su menú desplegable ofrece opciones adicionales:
  - **MPR 3D**: Abre la vista MPR 3D completa.
  - **Coronal**: Genera una reconstrucción coronal en línea en el visor.
  - **Sagital**: Genera una reconstrucción sagital en línea en el visor.
  - **Axial**: Genera una reconstrucción axial en línea en el visor.

- <BsFillBadge3dFill /> **Volumen 3D**: Abre la [vista de renderizado de volumen 3D](../volume/main.md) para la serie seleccionada.

- **Ayuda**: Abre el panel de Ayuda con la documentación completa. Su menú desplegable también ofrece acceso rápido al Panel de Ayuda, el Tour Guiado y los Atajos de teclado.

## Ventanas Estrechas

Cuando la ventana no es lo suficientemente ancha para mostrar todos los botones, la barra de herramientas agrupa las herramientas en menús. Los botones Abrir, Búsqueda de Estudio, Configuración, Cuadrícula y Ayuda permanecen visibles, y cada botón agrupado conserva sus propias opciones desplegables dentro de su menú:

- <RiToolsFill /> **Herramientas**: Contiene las herramientas de modo de ratón: Explorar Serie, Ventana de Imagen, Mover, Zoom y Medidas.
- <RiEyeLine /> **Vista**: Contiene Modo de Sincronización, Información de Pantalla, Restablecer, Transformaciones y Reproducir/Detener.
- <MdOpenInNew /> **Abrir**: Contiene MPR y Volumen 3D.
