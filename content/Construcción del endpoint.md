# Construcción del endpoint

A través de una API...

## Obtener perfiles de la organización

+ Definir criterios o filtros para determinar:
Perfiles activos e inactivos


### Informes de usuarios activos de Microsoft 365 
[Documentación completa](https://learn.microsoft.com/es-es/graph/api/reportroot-getoffice365activeuserdetail?view=graph-rest-1.0)
#### Descripción

Obtiene el número de usuarios por tipo de actividad y servicio.

#### Solicitud HTTP
Espacio de nombres: microsoft.graph

```
GET /reports/getOffice365ActiveUserDetail(period='{period_value}')
GET /reports/getOffice365ActiveUserDetail(date={date_value})
```
#### Requisitos

| Requisito  | Valor | Descripción |
| -----------| ----- | ----------- |
| Permiso |  Reports.Read.All | Delegado (cuenta profesional o educativa) |
| Parámetro de función  | period [string]   |  Especifica la duración de tiempo durante la que se agrega el informe. Los valores admitidos para {period_value} son: D7, D30, D90 y D180. Estos valores tienen el formato Dn, donde n representa el número de días durante los que se agrega el informe.   |
| Parámetro de función | date [fecha] | Especifica la fecha en que quiere ver los usuarios que realizaron alguna actividad. {date_value} necesita tener el formato de AAAA-MM-DD. Como este informe solo está disponible para los últimos 30 días, {date_value} tiene que ser una fecha de ese intervalo. |
| Encabezados de solicitud | Authorization | Portador {token}. Obligatorio. | 
	
#### Respuesta

De acuerdo a la documentación, si se ejecuta correctamente, este método devuelve una respuesta `302 Found` que redirige a una URL de descarga con autenticación previa para el informe. La URL se encuentra en el encabezado `Location` de la respuesta.

Las URL de descarga con autenticación previa solo son válidas durante un breve período de tiempo (unos minutos) y no necesitan un encabezado Authorization para descargarlas.

El archivo CSV contendrá una larga variedad de encabezados de columna, sin embargo, no todos son necesarios para la solución. A continuación se enlistan aquellos que son relevantes: 

+ Fecha de actualización del informe
+ Nombre principal de usuario
+ Nombre para mostrar
+ Eliminado
+ Fecha de eliminación
+ Fecha de la última actividad de Exchange
+ Fecha de la última actividad de OneDrive
+ Fecha de la última actividad de SharePoint
+ Fecha de la última actividad de Skype Empresarial
+ Fecha de la última actividad de Yammer
+ Fecha de la última actividad de Teams
+ Productos asignados

#### Ejemplo 

Use el parámetro de consulta $select para devolver un conjunto de propiedades diferente al predeterminado para un recurso individual o una colección de recursos. Con $select, puede especificar un subconjunto o un superconjunto de las propiedades predeterminadas.

## Obtener actividad de perfiles
Por rango de fechas definidas por el usuario
https://learn.microsoft.com/es-es/graph/api/resources/calendar?view=graph-rest-1.0&preserve-view=true
https://learn.microsoft.com/es-es/graph/api/calendar-list-calendarview?view=graph-rest-1.0&tabs=http

### Aplicaciones Microsoft 365 informes de uso
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





## Tiempo de actividades 
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

#### Descripción
#### Solicitud HTTP
```
GET
```
#### Requisitos

| Requisito  | Valor | Descripción |
| -----------| ----- | ----------- |
| Permiso |  Reports.Read.All | Delegado (cuenta profesional o educativa) |
| Parámetro de función  | period [string]   |  Especifica la duración de tiempo durante la que se agrega el informe. Los valores admitidos para {period_value} son: D7, D30, D90 y D180. Estos valores tienen el formato Dn, donde n representa el número de días durante los que se agrega el informe.   |
| Parámetro de función | date [fecha] | Especifica la fecha en que quiere ver los usuarios que realizaron alguna actividad. {date_value} necesita tener el formato de AAAA-MM-DD. Como este informe solo está disponible para los últimos 30 días, {date_value} tiene que ser una fecha de ese intervalo. |
| Encabezados de solicitud | Authorization | Portador {token}. Obligatorio. | 

#### Respuesta
#### Ejemplo

## Número de llamadas/chats

+ De cada usuario por fechas
	https://learn.microsoft.com/es-es/graph/api/reportroot-getteamsuseractivitycounts?view=graph-rest-1.0

#### Descripción
#### Solicitud HTTP
```
GET
```
#### Requisitos

| Requisito  | Valor | Descripción |
| -----------| ----- | ----------- |
| Permiso |  Reports.Read.All | Delegado (cuenta profesional o educativa) |
| Parámetro de función  | period [string]   |  Especifica la duración de tiempo durante la que se agrega el informe. Los valores admitidos para {period_value} son: D7, D30, D90 y D180. Estos valores tienen el formato Dn, donde n representa el número de días durante los que se agrega el informe.   |
| Parámetro de función | date [fecha] | Especifica la fecha en que quiere ver los usuarios que realizaron alguna actividad. {date_value} necesita tener el formato de AAAA-MM-DD. Como este informe solo está disponible para los últimos 30 días, {date_value} tiene que ser una fecha de ese intervalo. |
| Encabezados de solicitud | Authorization | Portador {token}. Obligatorio. | 

#### Respuesta
#### Ejemplo

### Tráfico de información 

Tipo y tamaño de archivo 

https://learn.microsoft.com/es-mx/training/modules/msgraph-access-file-data/2-access-files-onedrive
https://learn.microsoft.com/es-es/graph/api/itemactivitystat-getactivitybyinterval?view=graph-rest-1.0&tabs=http
https://learn.microsoft.com/es-es/graph/api/driveitem-list-children?view=graph-rest-1.0&tabs=http

https://graph.microsoft.com/v1.0/users/{userid}
https://graph.microsoft.com/v1.0/users/{userid}/drive
https://graph.microsoft.com/v1.0/users/1afcd080-0396-4846-85c6cfa221b27879/drive/root?$expand=children($select=id,name,size)
https://graph.microsoft.com/v1.0/users/1afcd080-0396-4846-85c6-cfa221b27879/drive/recent

#### Descripción
#### Solicitud HTTP
```
GET
```
#### Requisitos

| Requisito  | Valor | Descripción |
| -----------| ----- | ----------- |
| Permiso |  Reports.Read.All | Delegado (cuenta profesional o educativa) |
| Parámetro de función  | period [string]   |  Especifica la duración de tiempo durante la que se agrega el informe. Los valores admitidos para {period_value} son: D7, D30, D90 y D180. Estos valores tienen el formato Dn, donde n representa el número de días durante los que se agrega el informe.   |
| Parámetro de función | date [fecha] | Especifica la fecha en que quiere ver los usuarios que realizaron alguna actividad. {date_value} necesita tener el formato de AAAA-MM-DD. Como este informe solo está disponible para los últimos 30 días, {date_value} tiene que ser una fecha de ese intervalo. |
| Encabezados de solicitud | Authorization | Portador {token}. Obligatorio. | 

#### Respuesta
#### Ejemplo


https://learn.microsoft.com/es-es/graph/reportroot-authorization
