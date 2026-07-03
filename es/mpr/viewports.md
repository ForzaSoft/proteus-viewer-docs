# Ventanas

La pantalla MPR se divide en hasta tres ventanas, cada una mostrando el volumen reconstruido a lo largo de un plano anatómico diferente.

## Planos

- **Axial**: Secciones transversales horizontales (vista de arriba abajo).
- **Sagital**: Secciones transversales verticales (vista lateral).
- **Coronal**: Secciones transversales verticales (vista frontal).

## Diseño

Use el botón <RiGridFill /> **Cuadrícula** en la barra de herramientas para elegir cómo se disponen las tres ventanas en pantalla. Los diseños disponibles son:

- **2 Columnas [2|1]** / **2 Columnas [1|2]**: Diseños de dos columnas con una ventana mayor y otra menor.
- **3 Columnas**: Las tres ventanas mostradas una junto a la otra.
- **2 Filas [2|1]** / **2 Filas [1|2]**: Diseños de dos filas con una ventana mayor y otra menor.
- **3 Filas**: Las tres ventanas apiladas verticalmente.

## Maximizar una Ventana

Haga doble clic en cualquier ventana para expandirla a pantalla completa. Haga doble clic de nuevo para restaurar el diseño multiventana.

## Modo de Renderizado

Cada ventana tiene un modo de renderizado independiente, configurado con el botón <RiExpandHeightFill /> **Modo de Renderizado** en la barra de herramientas mientras esa ventana está activa:

- **MPR**: Reconstrucción multiplanar estándar.
- **MIP**: Proyección de Intensidad Máxima — muestra los vóxeles más brillantes a lo largo de cada rayo, útil para resaltar estructuras densas (p. ej. vasos, huesos).
- **MinIP**: Proyección de Intensidad Mínima — muestra los vóxeles más oscuros a lo largo de cada rayo, útil para resaltar estructuras llenas de aire.
- **Avg**: Proyección de Intensidad Media — promedia todos los valores de vóxel a lo largo de cada rayo.
