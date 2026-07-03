# Configuración

El cuadro de diálogo de Configuración permite definir el comportamiento de la aplicación y su conexión con el PACS. Ábralo con el botón <BiCog /> **Configuración** de la barra de herramientas.

La configuración se organiza en dos pestañas: **General** y **DICOM**. Haga clic en **Guardar** para aplicar los cambios o en **Cancelar** para descartarlos.

## General

La configuración general controla el comportamiento global de la aplicación.

- **Nivel de Registros**: Controla el nivel de detalle que la aplicación guarda en sus registros. Elija **Info** para el uso normal, **Debug** para diagnóstico detallado o **Error** para registrar solo los fallos.

## DICOM

La pestaña DICOM configura el nodo local y las Ubicaciones PACS remotas utilizadas para consultar y recuperar estudios.

### Nodo local

Estos ajustes identifican esta aplicación en la red DICOM. El PACS remoto debe estar configurado para aceptar este nodo.

- **AE Title Local**: El Application Entity Title que identifica este nodo ante los PACS remotos.
- **Puerto SCP Local**: El puerto en el que este nodo escucha las asociaciones DICOM entrantes.

### Ubicaciones PACS

Una **Ubicación** es un PACS remoto que la aplicación puede consultar y del que puede recuperar estudios. Para conectarse a un PACS nuevo debe agregar una Ubicación con sus datos de conexión.

Para agregar una Ubicación:

1. Haga clic en **+ Ubicación**.
2. Complete la fila:
   - **Nombre**: Una etiqueta para identificar la Ubicación.
   - **IP**: El nombre de host o la dirección IP del PACS remoto.
   - **Puerto**: El puerto en el que escucha el PACS remoto.
   - **AE Title**: El Application Entity Title del PACS remoto.
3. Haga clic en **Guardar**.

Para eliminar una Ubicación, haga clic en el botón de borrar <RiDeleteBin7Fill /> de su fila.

> **El PACS remoto debe ser compatible con DICOM C-GET.** Los estudios se recuperan mediante el servicio C-GET. Si el PACS solo admite C-MOVE, la recuperación fallará.
