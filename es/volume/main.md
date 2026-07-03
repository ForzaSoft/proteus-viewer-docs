# Volumen 3D

La vista de Volumen 3D renderiza una serie de TC como un volumen tridimensional interactivo. Ábrala desde el visor con el botón <BsFillBadge3dFill /> **Volumen 3D** de la barra de herramientas — la serie seleccionada se abre en una nueva ventana. El volumen se carga progresivamente; el pie de página muestra el progreso de descarga hasta que todos los cortes están disponibles.

## Barra de Herramientas

- <RiDownload2Fill /> **Descargar Imagen**: Guarda la vista 3D actual como una imagen PNG.

- <RiInformationLine /> **Información de Pantalla** (**Shift + A**): Muestra u oculta las anotaciones en pantalla.

### Modos de Ratón

Seleccione una herramienta y luego haga clic y arrastre sobre el volumen:

- <LuRotate3D /> **Rotación 3D** (**R**): Rota el volumen en tres dimensiones.

- <RiContrastFill /> **Ventana de Imagen** (**W**): Ajusta la ventana para cambiar qué densidades de tejido son visibles.

- <LuRotateCcw /> **Giro** (**T**): Rota el volumen alrededor del eje de visualización.

- <RiDragMove2Fill /> **Mover** (**M**): Reposiciona el volumen dentro de la ventana.

- <RiZoomInLine /> **Zoom** (**Z**): Amplía o reduce el volumen.

### Vista

- <RiArrowGoBackFill /> **Restablecer** (**Shift + R**): Devuelve el volumen a su orientación, posición, zoom y ventana iniciales.

- <RiPaletteLine /> **Preajustes 3D**: Selecciona el preajuste de renderizado, que controla los colores y la opacidad aplicados a las distintas densidades de tejido:
  - **Tejido blando y piel** (predeterminado): Renderizado de tejido blando con la superficie de la piel.
  - **Hueso y piel**: Estructuras óseas con una superficie de piel translúcida.
  - **Vías aéreas**: Estructuras con aire como la tráquea y los bronquios.
  - **Huesos**: Solo estructuras óseas.
  - **Sombreado**: Activa o desactiva el sombreado de superficie del preajuste actual, añadiendo profundidad al renderizado.
