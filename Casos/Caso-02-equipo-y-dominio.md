# Equipo no reconocido en el dominio

Problema: 
* El equipo cliente Windows 10 no logra unirse ni ser reconocido por el dominio en Windows Server.

Entorno:
* Servidor: Windows Server 2019 (Maquina Virtual - laboratorio)
* Cliente: Windows 10 (Maquina Virtual - laboratorio)
* Virtualización: VirtualBox

Diagnóstico:
* Se detecta que el servicio DHCP se encuentra activo tanto en el servidor como en el equipo cliente.
* El equipo cliente no obtiene servidor DNS, lo que impide la resolución del dominio.
* El servidor no muestra concesiones activas del cliente.

Solución:
* Se configuró una IP estática en el servidor, asignando como DNS la IP del propio servidor.
* En el equipo cliente se ejecutaron los comandos:
	- ipconfig /release
	- ipconfig /renew
* Se verificó la correcta asignación de IP y DNS desde el cliente

Resultado:
* El equipo cliente obtiene correctamente IP y DNS desde el servidor.
* Se logra unir exitosamente el equipo al dominio.
* El servidor reconoce al equipo dentro de Active Directory.
