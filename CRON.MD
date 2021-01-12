**¿Qué es CRON?**

Es un administrador regular de procesos en segundo plano que ejecuta procesos o guiones a intervalos regulares por ejemplo, cada minuto, día, semana o mes.

**¿Qué es CRONTAB?**

Crontab es un simple archivo de texto que guarda una lista de comandos a ejecutar en un tiempo especificado por el usuario. Crontab verificará la fecha y hora en que se debe ejecutar el script

**¿Qué hace cada línea de cron?**

**30 * * * * /home/prueba.sh**

Ejecuta el script todos los dias y todas horas en el minuto 30

**30 20 * * * /home/prueba.sh**

Ejecuta el script todos los dias a las ocho y media

**30 20 * * 1-5 /home/prueba.sh**

Ejecuta el script de lunes a viernes a las ocho y media

**30 20 * * 2,4 /home/prueba.sh**

Ejecuta el script todos los martes y jueves a las ocho y media

**30 20 10,20 * * /home/prueba.sh**

Ejecuta el script los dias 10 y 20 a las ocho y media

***/15 * * * * /home/prueba.sh**

Ejecuta el script cada 15 minutos

**@daily /home/prueba.sh**

Ejecuta el script cada dia

**@monthly /etc/backup.sh**

Ejecuta el script cada mes

**30 20 * * Mon-Fri /etc/test.sh**

Ejecuta el script de lunes a viernes a las ocho y media

**1 0 1-7 * * [ "$(date '+%a')" = "Fri" ] && /etc/backup.sh**

Ejecuta el script del dia 1 al 7 a las 00:01 si es viernes y existe el archivo backup.sh

**Queremos que se guarde el siguiente contenido en un fichero cada 5 minutos de lunes a viernes, donde Ubuntu, es el nombre de usuario con el que accedemos y la fecha y hora sean del sistema.**

Lo primero de todo creo el script

![](https://raw.githubusercontent.com/GalderGG/fotosDocumentacion2/master/1.png)

Despues hay que cambiarle los permisos al script

![](https://raw.githubusercontent.com/GalderGG/fotosDocumentacion2/master/2.png)

Ahora creo el archivo date.txt para guardar las respuestas del script

![](https://raw.githubusercontent.com/GalderGG/fotosDocumentacion2/master/3.png)

Por ultimo añado esta ultima linea en el archivo de crontab

![](https://raw.githubusercontent.com/GalderGG/fotosDocumentacion2/master/4.png)

Resultado:

![](https://raw.githubusercontent.com/GalderGG/fotosDocumentacion2/master/6.png)

*Para entrar en archivo de crontab

![](https://raw.githubusercontent.com/GalderGG/fotosDocumentacion2/master/5.png)

**Crear un cron para que haga una copia (en un fichero comprimido) de la carpeta /home/ubuntu en la carpeta /copias cada 15 minutos los martes.**