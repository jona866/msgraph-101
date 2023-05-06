# Número de llamadas o chats

+ De cada usuario por fechas
	https://learn.microsoft.com/es-es/graph/api/reportroot-getteamsuseractivitycounts?view=graph-rest-1.0

## Descripción

Obtener el número de actividades de Microsoft Teams por tipo de actividad. Las actividades las realizan los usuarios con licencia de Microsoft Teams.

## Solicitud HTTP
```
GET /reports/getTeamsUserActivityCounts(period='{period_value}')
```
## Requisitos

| Requisito  | Valor | Descripción |
| -----------| ----- | ----------- |
| Permiso |  Reports.Read.All | Delegado (cuenta profesional o educativa) |
| Parámetro de función  | period [string]   |  Especifica la duración de tiempo durante la que se agrega el informe. Los valores admitidos para {period_value} son: D7, D30, D90 y D180. Estos valores tienen el formato Dn, donde n representa el número de días durante los que se agrega el informe.   |
| Encabezados de solicitud | Authorization | Portador {token}. Obligatorio. | 
## Respuesta
El archivo CSV tiene los siguientes encabezados de columna:

+ Fecha de actualización del informe
+ Fecha del informe
+ Mensajes de chat del equipo
+ Mensajes de publicación
+ Mensajes de respuesta
+ Mensajes de chat privados
+ Llamadas
+ Reuniones
+ Duración de audio
+ Duración del vídeo
+ Duración del recurso compartido de pantalla
+ Reuniones organizadas
+ Reuniones atendidas
+ Período del informe

## Ejemplo
 Un ejemplo de solicitud puede ser 
 
```
GET https://graph.microsoft.com/v1.0/reports/getTeamsUserActivityCounts(period='D7')
```