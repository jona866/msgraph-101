# Construcción del endpoint

A través de una API...

+ Obtener perfiles de la organización
	Definir criterios o filtros para determinar:
	Perfiles activos 
	Perfiles inactivos

+ Obtener actividad de perfiles 
	Por rango de fechas definidas por el usuario

+ Tiempo de actividades 
	Teams
	Outlook
	Sharepoint
	Yammer/Viva engage 
	Llamadas/Mensajes

+ Número de llamadas/chats
	De cada usuario por fechas

+Tráfico de información 
	Tipo y tamaño de archivo 

https://graph.microsoft.com/v1.0/users/{userid}
https://graph.microsoft.com/v1.0/users/{userid}/drive
https://graph.microsoft.com/v1.0/users/1afcd080-0396-4846-85c6cfa221b27879/drive/root?$expand=children($select=id,name,size)
https://graph.microsoft.com/v1.0/users/1afcd080-0396-4846-85c6-cfa221b27879/drive/recent



