# Construcción del endpoint

A través de una API...

+ Obtener perfiles de la organización
	Definir criterios o filtros para determinar:
	Perfiles activos 
	Perfiles inactivos
	https://learn.microsoft.com/es-es/graph/api/reportroot-getoffice365activeuserdetail?view=graph-rest-1.0

+ Obtener actividad de perfiles 
	Por rango de fechas definidas por el usuario
	https://learn.microsoft.com/es-es/graph/api/resources/calendar?view=graph-rest-1.0&preserve-view=true
	https://learn.microsoft.com/es-es/graph/api/calendar-list-calendarview?view=graph-rest-1.0&tabs=http

+ Tiempo de actividades 
	Teams
	Outlook
	Sharepoint
	Yammer/Viva engage 
	Llamadas/Mensajes
	https://learn.microsoft.com/es-es/graph/outlook-get-shared-events-calendars
	https://learn.microsoft.com/es-es/graph/api/resources/report?view=graph-rest-1.0


https://learn.microsoft.com/es-es/graph/api/calendar-list-calendarview?view=graph-rest-1.0&tabs=http
+ Número de llamadas/chats
	De cada usuario por fechas
	https://learn.microsoft.com/es-es/graph/api/reportroot-getteamsuseractivitycounts?view=graph-rest-1.0

+ Tráfico de información 
	Tipo y tamaño de archivo 
	https://learn.microsoft.com/es-mx/training/modules/msgraph-access-file-data/2-access-files-onedrive
	https://learn.microsoft.com/es-es/graph/api/itemactivitystat-getactivitybyinterval?view=graph-rest-1.0&tabs=http
	https://learn.microsoft.com/es-es/graph/api/driveitem-list-children?view=graph-rest-1.0&tabs=http

https://graph.microsoft.com/v1.0/users/{userid}
https://graph.microsoft.com/v1.0/users/{userid}/drive
https://graph.microsoft.com/v1.0/users/1afcd080-0396-4846-85c6cfa221b27879/drive/root?$expand=children($select=id,name,size)
https://graph.microsoft.com/v1.0/users/1afcd080-0396-4846-85c6-cfa221b27879/drive/recent



