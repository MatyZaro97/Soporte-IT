# Usuario no inicia sesión en dominio 

Escenario: 
Usuario no puede loguearse con su cuenta de dominio en una PC corporativa.

Diagnostico:
• El usuario no logra iniciar sesión en el dominio.
• Se verifica que el servidor de dominio funciona correctamente como DNS.
• Desde la máquina servidor:
  - ping 192.168.100.2 (DC) → respuesta correcta.
  - ping 192.168.100.3 (cliente) → sin respuesta.
  - nslookup redinterna.local → resuelve correctamente el dominio.
• Desde la máquina del usuario:
  - nslookup redinterna.local → no obtiene información del dominio.
• Se detecta que la PC del usuario no estaba configurada para usar el DNS del dominio.

Solución:
• Se configura correctamente el DNS en la PC del usuario, apuntando al servidor de dominio.
• Se limpio la caché con el comando: 
  - **ipconfig /flushdns**
• Se reinicia la máquina y se intenta nuevamente el inicio de sesión.

Resultado:
• PC del usuario logra resolver el dominio correctamente.
• El usuario puede iniciar sesión en el dominio sin incovenientes. 

