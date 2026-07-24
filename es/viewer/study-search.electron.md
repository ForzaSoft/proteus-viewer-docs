# Búsqueda de Estudios

El cuadro de diálogo de Búsqueda de Estudios es donde se buscan y abren los estudios. Ábralo con el botón <RiDatabase2Fill /> **Búsqueda de Estudio** de la barra de herramientas. El botón tiene dos ámbitos y ambos usan el mismo cuadro de diálogo:

- **Remoto**: las Ubicaciones PACS configuradas en la Configuración. Es lo que abre el botón al hacer clic directamente.
- **Local**: los estudios almacenados en este equipo.

Al hacer clic en el botón se abre el ámbito Remoto; use la flecha contigua para elegir **Remoto** o **Local**. El título del cuadro de diálogo indica el ámbito activo, y al cambiar de ámbito se limpian los filtros y los resultados.

## Filtros

Ambos ámbitos comparten los mismos filtros:

- **Fuente**: qué nodo se consulta. En el ámbito Remoto lista las Ubicaciones PACS configuradas, y está vacía si no hay ninguna. En el ámbito Local queda fijada en **Local** y no se puede cambiar.
- **Modalidad**: marque una o varias modalidades, o **Todas las Modalidades**.
- **Rango de fechas**: **Todas las Fechas**, un rango predefinido (Hoy, Ayer, Última Semana, Último Mes, Último Año), **Fecha Personalizada** para un solo día o **Rango Personalizado** entre dos fechas. Los dos campos de fecha solo se pueden editar en las opciones personalizadas.
- **Campo de búsqueda**: elija con qué comparar — ID del Paciente, Nombre del Paciente, Número de Acceso, Descripción del Estudio, Médico Remitente o Nombre de la Institución — y escriba el valor. El texto se compara de forma parcial, así que basta con un fragmento.

Pulse **Buscar** (o Enter en el campo de texto) para ejecutar la consulta, y **Limpiar** para restablecer todos los filtros.

El ámbito Local lista todos los estudios almacenados en cuanto se abre el cuadro de diálogo, porque la consulta la responde la base de datos local. El ámbito Remoto espera a que pulse **Buscar**: una consulta sin filtros contra todas las Ubicaciones PACS sería lenta.

## Resultados

Los estudios encontrados se listan con paciente, fecha, modalidades, descripción y la fuente de la que provienen. Seleccione un estudio para listar sus series debajo.

Para abrir un estudio:

- **Haga doble clic** sobre él, o selecciónelo y pulse **Abrir**.
- **Haga clic derecho** para **Abrir estudio** (reemplaza lo que esté abierto) o **Añadir estudio** (lo abre junto a los estudios actuales).

Un estudio abierto desde una Ubicación PACS se descarga a medida que lo visualiza y no se conserva al cerrar la aplicación — vea a continuación cómo conservarlo.

## Guardar estudios en el almacenamiento local

- **Guardar en Local** (ámbito Remoto): descarga el estudio seleccionado directamente al almacenamiento local sin abrirlo. Junto al botón se muestra el porcentaje de progreso, y el estudio queda disponible en el ámbito Local al terminar.
- <RiSave3Fill /> **Guardar en Local** (barra de herramientas): conserva el estudio que está visualizando, cuando proviene de una Ubicación PACS o de archivos. El estudio permanece abierto mientras se guarda.
- **Importar** (ámbito Local): agrega archivos DICOM de este equipo al almacenamiento local — **Importar Archivos...** para uno o varios archivos, **Importar Carpeta...** para una carpeta completa, que se recorre de forma recursiva. Los archivos que no son DICOM se omiten. La lista de estudios se actualiza al terminar la importación.

Guardar el mismo estudio dos veces no causa problemas: las imágenes existentes se actualizan en lugar de duplicarse.

## Eliminar estudios

**Eliminar** quita el estudio seleccionado del almacenamiento local, incluidos sus archivos DICOM guardados. Solo está habilitado para los estudios que residen allí, y la acción no se puede deshacer.

La carpeta que contiene estos estudios se muestra, en modo de solo lectura, como **Ruta de Almacenamiento DICOM Local (solo lectura)** en la [Configuración](./settings.electron.md).
