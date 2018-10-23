
Instituto Politécnico Nacional  
ESCOM  
Escuela Superior de Computo  

Integrantes:  
García Cebada Jorge Miguel  
Amador Nava Miguel Ángel  

Materia: Embedded Systems  
Profesor: Victor Hugo García Ortega  
Grupo: 3CV10  

![alt tag](rasp.jpg)  
  
Escritorio Raspberry:  
![alt tag](1Escritorio.png)  

Métodos de conexión  


Conexión de Red  


$ sudo nano /etc/wpa_supplicant/wpa_supplicant.conf  

![alt tag](2Conexion.png)  



1. Conexion SSH  

En la Raspberry:

$ sudo systemctl status ssh  
$ sudo systemctl start ssh  
$ sudo systemctl enable ssh  

![alt tag](3sshpi.png)  

En la computadora  

$ nmap -p22 192.168.1.0/24  

![alt tag](4nmapcpu.png)  

Teniendo el valor de la ip de la raspberry 192.168.1.74 (siendo la ultima valida en la lista nmap).  

$ ssh pi@192.168.1.74  

![alt tag](4sshcpu.png)  



2. Conexion VNC  

En la Raspberry:  

$ sudo systemctl status vncserver-x11-serviced  
$ sudo systemctl start vncserver-x11-serviced  
$ sudo systemctl enable vncserver-x11-serviced  

![alt tag](5vncpi.png)  

En la computadora:  
  
Instalar VNC Connect en la computadora  

Correr el programa y crear nueva conexión, ingresando los datos pertinentes:  

![alt tag](5progcpu.png)  

![alt tag](5progcpu2.png)  

![alt tag](5vnccpu.png)  




3. Conexion UART  

En la Raspberry:  

$ sudo nano/boot/config.txt

enable_uart=1
core_freq=250

![alt tag](6filepi.png)  

En el Hardware:  

![alt tag](6hardtable.png)  

![alt tag](6hard.jpg)  

En la computadora:  

$ ls -l /dev/ttyUSB0  
$sudo usermod -a -G dialout "$(whoami)"  
$ sudo screen/dev/ttyUSB0 115200  

![alt tag](6comcpu.png)  

Al resetear la Raspberry:  

![alt tag](6uart.png)  

Raspberry Pi 3B+



