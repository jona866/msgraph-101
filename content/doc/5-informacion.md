# Tráfico de información 

Tipo y tamaño de archivo 

https://learn.microsoft.com/es-mx/training/modules/msgraph-access-file-data/2-access-files-onedrive
https://learn.microsoft.com/es-es/graph/api/itemactivitystat-getactivitybyinterval?view=graph-rest-1.0&tabs=http
https://learn.microsoft.com/es-es/graph/api/driveitem-list-children?view=graph-rest-1.0&tabs=http

https://graph.microsoft.com/v1.0/users/{userid}
https://graph.microsoft.com/v1.0/users/{userid}/drive
https://graph.microsoft.com/v1.0/users/1afcd080-0396-4846-85c6cfa221b27879/drive/root?$expand=children($select=id,name,size)
https://graph.microsoft.com/v1.0/users/1afcd080-0396-4846-85c6-cfa221b27879/drive/recent

## Descripción

Obtiene información sobre el uso de OneDrive por cuenta.

## Solicitud HTTP
```
GET /reports/getOneDriveUsageAccountDetail(period='{period_value}')
GET /reports/getOneDriveUsageAccountDetail(date={date_value})
```
## Requisitos

| Requisito  | Valor | Descripción |
| -----------| ----- | ----------- |
| Permiso |  Reports.Read.All | Delegado (cuenta profesional o educativa) |
| Parámetro de función  | period [string]   |  Especifica la duración de tiempo durante la que se agrega el informe. Los valores admitidos para {period_value} son: D7, D30, D90 y D180. Estos valores tienen el formato Dn, donde n representa el número de días durante los que se agrega el informe.   |
| Parámetro de función | date [fecha] | Especifica la fecha en que quiere ver los usuarios que realizaron alguna actividad. {date_value} necesita tener el formato de AAAA-MM-DD. Como este informe solo está disponible para los últimos 30 días, {date_value} tiene que ser una fecha de ese intervalo. |
| Encabezados de solicitud | Authorization | Portador {token}. Obligatorio. | 

## Respuesta
El archivo CSV tiene los siguientes encabezados de columna.

+ Fecha de actualización del informe
+ Dirección URL del sitio
+ Nombre para mostrar del propietario
+ Eliminado
+ Fecha de la última actividad
+ Número de archivos
+ Número de archivos activos
+ Almacenamiento usado (bytes)
+ Almacenamiento asignado (bytes)
+ Nombre principal de propietario
+ Período del informe
## Ejemplo

[Docuentación completa](https://learn.microsoft.com/es-es/graph/api/reportroot-getonedriveusageaccountdetail?view=graph-rest-1.0)

[Sharepoint](https://learn.microsoft.com/es-es/graph/api/reportroot-getsharepointsiteusagedetail?view=graph-rest-1.0)
