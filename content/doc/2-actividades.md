# Actividades por perfil
## Aplicaciones Microsoft 365 informes de uso
[Documentación completa](https://learn.microsoft.com/es-es/graph/api/reportroot-getm365appuserdetail?view=graph-rest-1.0&tabs=http)
#### Descripción
#### Solicitud HTTP
```
GET /reports/getM365AppUserDetail(period='{period_value}')
GET /reports/getM365AppUserDetail(date='{date_value}') 
```
#### Requisitos

| Requisito  | Valor | Descripción |
| -----------| ----- | ----------- |
| Permiso |  Reports.Read.All | Delegado (cuenta profesional o educativa) |
| Parámetro de función  | period [string]   |  Especifica la duración de tiempo durante la que se agrega el informe. Los valores admitidos para {period_value} son: D7, D30, D90 y D180. Estos valores tienen el formato Dn, donde n representa el número de días durante los que se agrega el informe.   |
| Parámetro de función | date [fecha] | Especifica la fecha en que quiere ver los usuarios que realizaron alguna actividad. {date_value} necesita tener el formato de AAAA-MM-DD. Como este informe solo está disponible para los últimos 30 días, {date_value} tiene que ser una fecha de ese intervalo. |
| Encabezados de solicitud | Authorization | Portador {token}. Obligatorio. | 

#### Respuesta
El tipo de salida predeterminado es text/csv. Sin embargo, si desea especificar el tipo de salida, puede usar el parámetro de consulta OData $format para establecer la salida predeterminada en text/csv o application/json. 
##### CSV
Si se ejecuta correctamente, este método devuelve una respuesta 302 Found que redirige a una URL de descarga con autenticación previa para el informe. La URL se encuentra en el encabezado Location de la respuesta.

Las URL de descarga con autenticación previa solo son válidas durante un breve período de tiempo (unos minutos) y no necesitan un encabezado Authorization para descargarlas.

El archivo CSV tiene los siguientes encabezados de columna:

+ Fecha de actualización del informe
+ Nombre principal de usuario
+ Última fecha de activación
+ Fecha de la última actividad
+ Período del informe
+ Windows
+ Mac
+ Móvil
+ Web
+ Outlook
+ Word
+ Excel
+ PowerPoint
+ OneNote
+ Teams
+ Outlook (Windows)
+ Word (Windows)
+ Excel (Windows)
+ PowerPoint (Windows)
+ OneNote (Windows)
+ Teams (Windows)
+ Outlook (Mac)
+ Word (Mac)
+ Excel (Mac)
+ PowerPoint (Mac)
+ OneNote (Mac)
+ Teams (Mac)
+ Outlook (móvil)
+ Word (móvil)
+ Excel (móvil)
+ PowerPoint (móvil)
+ OneNote (móvil)
+ Teams (móvil)
+ Outlook (Web)
+ Word (Web)
+ Excel (Web)
+ PowerPoint (Web)
+ OneNote (Web)
+ Teams (Web)
##### JSON
Si se ejecuta correctamente, este método devuelve un 200 OK código de respuesta y un objeto JSON en el cuerpo de la respuesta.

El tamaño de página predeterminado para esta solicitud es de 200 elementos.
#### Ejemplo

#### Recursos
https://learn.microsoft.com/es-es/graph/api/resources/calendar?view=graph-rest-1.0&preserve-view=true
https://learn.microsoft.com/es-es/graph/api/calendar-list-calendarview?view=graph-rest-1.0&tabs=http
