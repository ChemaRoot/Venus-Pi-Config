# Venus-Pi-Config
Manual puesta en marcha Venus OS

1)Tener Acceso Root
•	Entrar en pestaña General 
•	Seleccionar Usuario e Instalador
•	Contraseña: ZZZ
•	Sin entrar en la selección de usuario mantener pulsado flecha derecha unos segundos
•	Cambiar contraseña Root

2)Modo Grafico VENUS OS HDMI OUTPUT
•	Añadir lo siguiente en config.txt
	framebuffer_width=800
	framebuffer_height=480
•	Conectarse por ssh y ejecutar
	mv /etc/venus/headless /etc/venus/headless.off

3) Habilitar CAN BUS
•	Ejecutar los siguientes comandos
	ln -s /opt/victronenergy/can-bus-bms/service /service/can-bus-bms.can0
	ln -s /opt/victronenergy/dbus-motordrive/service /service/dbus-motordrive.can0
	ln -s /opt/victronenergy/dbus-valence/service /service/dbus-valence.can0
	ln -s /opt/victronenergy/vecan-dbus/service /service/vecan-dbus.can0
	ln -s /opt/victronenergy/mqtt-n2k/service /service/mqtt-n2k.can0
	
•	Cambiar "DEV" por "can0" en las rutas /service/xxx.can0/run y en /service/xxx.can0/log/run
