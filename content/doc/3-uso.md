# Tiempo de actividades

+ Teams
+ Outlook https://learn.microsoft.com/es-es/graph/api/reportroot-getemailactivityuserdetail?view=graph-rest-1.0


+ Sharepoint
https://learn.microsoft.com/es-es/graph/api/reportroot-getsharepointactivityuserdetail?view=graph-rest-1.0
+ Yammer/Viva engage https://learn.microsoft.com/es-es/graph/api/reportroot-getyammeractivityuserdetail?view=graph-rest-1.0&tabs=http

+ Llamadas/Mensajes https://learn.microsoft.com/es-es/graph/api/reportroot-getteamsuseractivitycounts?view=graph-rest-1.0 o este https://learn.microsoft.com/es-es/graph/api/reportroot-getteamsuseractivityuserdetail?view=graph-rest-1.0

Más


https://learn.microsoft.com/es-es/graph/outlook-get-shared-events-calendars
https://learn.microsoft.com/es-es/graph/api/resources/report?view=graph-rest-1.0

https://learn.microsoft.com/es-es/graph/api/calendar-list-calendarview?view=graph-rest-1.0&tabs=http

## Descripción
## Solicitud HTTP

### Teams
```
GET /reports/getTeamsUserActivityUserDetail(period='{period_value}')
GET /reports/getTeamsUserActivityUserDetail(date={date_value})
```

### Outlook
```
GET /reports/getEmailActivityUserDetail(period='{period_value}')
GET /reports/getEmailActivityUserDetail(date={date_value})
```
### Sharepoint 
```
GET /reports/getSharePointActivityUserDetail(period='{period_value}')
GET /reports/getSharePointActivityUserDetail(date={date_value})
```
### Yammer
```
GET /reports/getYammerActivityUserDetail(period='{period_value}')
GET /reports/getYammerActivityUserDetail(date={date_value})
```
## Requisitos

| Requisito  | Valor | Descripción |
| -----------| ----- | ----------- |
| Permiso |  Reports.Read.All | Delegado (cuenta profesional o educativa) |
| Parámetro de función  | period [string]   |  Especifica la duración de tiempo durante la que se agrega el informe. Los valores admitidos para {period_value} son: D7, D30, D90 y D180. Estos valores tienen el formato Dn, donde n representa el número de días durante los que se agrega el informe.   |
| Parámetro de función | date [fecha] | Especifica la fecha en que quiere ver los usuarios que realizaron alguna actividad. {date_value} necesita tener el formato de AAAA-MM-DD. Como este informe solo está disponible para los últimos 30 días, {date_value} tiene que ser una fecha de ese intervalo. |
| Encabezados de solicitud | Authorization | Portador {token}. Obligatorio. | 

## Respuesta

### Teams
El archivo CSV tiene los siguientes encabezados de columna.

+ Fecha de actualización del informe
+ Nombre para mostrar del inquilino
+ Nombres para mostrar de inquilinos de canal compartido
+ User Id
+ Nombre principal de usuario
+ Fecha de la última actividad
+ Eliminado
+ Fecha de eliminación
+ Productos asignados
+ Recuento de mensajes de chat del equipo
+ Recuento de mensajes de chat privado
+ Recuento de llamadas
+ Recuento de reuniones
+ Mensajes de publicación
+ Mensajes de respuesta
+ Mensajes urgentes
+ Recuento organizado de reuniones
+ Recuento de reuniones atendidas
+ Recuento organizado de reuniones ad hoc
+ Recuento de reuniones ad hoc atendidas
+ Recuento organizado de reuniones únicas programadas
+ Recuento de reuniones atendidas de una sola vez programadas
+ Recuento organizado de reuniones periódicas programadas
+ Recuento programado de reuniones periódicas atendidas
+ Duración de audio
+ Duración del vídeo
+ Duración del recurso compartido de pantalla
+ Duración del audio en segundos
+ Duración del vídeo en segundos
+ Duración del recurso compartido de pantalla en segundos
+ Tiene otra acción
+ Tiene licencia
+ Período del informe

### Outlook
 
El archivo CSV tiene los siguientes encabezados de columna.

+ Fecha de actualización del informe
+ Nombre principal de usuario
+ Nombre para mostrar
+ Eliminado
+ Fecha de eliminación
+ Fecha de la última actividad
+ Número de envíos
+ Número de recepciones
+ Número de lecturas
+ Recuento de reuniones creadas
+ Recuento de interacciones en reunión
+ Productos asignados
+ Período del informe

### Sharepoint

El archivo CSV tiene los siguientes encabezados de columna.

+ Fecha de actualización del informe
+ Nombre principal de usuario
+ Eliminado
+ Fecha de eliminación
+ Fecha de la última actividad
+ Número de archivos vistos o editados
+ Número de archivos sincronizados
+ Número de archivos compartidos internamente
+ Número de archivos compartidos externamente
+ Número de páginas visitadas
+ Productos asignados
+ Período del informe

### Yammer

+ Fecha de actualización del informe
+ Nombre principal de usuario
+ Nombre para mostrar
+ Estado del usuario
+ Fecha de cambio de estado
+ Fecha de la última actividad
+ Número de publicaciones
+ Número de lecturas
+ Número de etiquetados como “Me gusta”
+ Productos asignados
+ Período del informe

## Ejemplo