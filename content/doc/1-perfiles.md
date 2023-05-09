# Perfiles de la organización 

## Informes de usuarios activos de Microsoft 365 
[Documentación completa](https://learn.microsoft.com/es-es/graph/api/reportroot-getoffice365activeuserdetail?view=graph-rest-1.0)
## Descripción

Obtiene el número de usuarios por tipo de actividad y servicio.

## Solicitud HTTP
Espacio de nombres: microsoft.graph

```
GET /reports/getOffice365ActiveUserDetail(period='{period_value}')
GET /reports/getOffice365ActiveUserDetail(date={date_value})
```
## Requisitos

| Requisito  | Valor | Descripción |
| -----------| ----- | ----------- |
| Permiso |  Reports.Read.All | Delegado (cuenta profesional o educativa) |
| Parámetro de función  | period [string]   |  Especifica la duración de tiempo durante la que se agrega el informe. Los valores admitidos para {period_value} son: D7, D30, D90 y D180. Estos valores tienen el formato Dn, donde n representa el número de días durante los que se agrega el informe.   |
| Parámetro de función | date [fecha] | Especifica la fecha en que quiere ver los usuarios que realizaron alguna actividad. {date_value} necesita tener el formato de AAAA-MM-DD. Como este informe solo está disponible para los últimos 30 días, {date_value} tiene que ser una fecha de ese intervalo. |
| Encabezados de solicitud | Authorization | Portador {token}. Obligatorio. | 
	
## Respuesta

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

## Ejemplo 

Solicitud

```
GET https://graph.microsoft.com/v1.0/reports/getOffice365ActiveUserDetail(period='D7') 
```



Use el parámetro de consulta $select para devolver un conjunto de propiedades diferente al predeterminado para un recurso individual o una colección de recursos. Con $select, puede especificar un subconjunto o un superconjunto de las propiedades predeterminadas.



[Extra](https://learn.microsoft.com/es-es/graph/api/calendar-getschedule?view=graph-rest-1.0&tabs=http)