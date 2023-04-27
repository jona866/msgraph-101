# Uso de la API

En base al  caso de estudio, podemos resumir las funcionalidades que se buscan en Microsoft Graph como:

## Obteneción de perfiles de la organización

Donde será necesario definir criterios o filtros para determinar qué perfiles están activos o inactivos. 

[Informes de usuarios activos de Microsoft 365](../content/doc/1-perfiles.md)

## Obteneción de actividades de los perfiles

Esto implica la obtención de datos por rango de fechas definidas por el usuario.

[Aplicaciones Microsoft 365 informes de uso](../content/doc/2-actividades.md)


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



## Número de llamadas/chats

+ De cada usuario por fechas
	https://learn.microsoft.com/es-es/graph/api/reportroot-getteamsuseractivitycounts?view=graph-rest-1.0



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
