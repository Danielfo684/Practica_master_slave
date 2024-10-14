# Practica_master_slave
Repositorio para la práctica de despliegue de aplicaciones web.

1. Inicializamos el archivo Vagrantfile con `vagrant init`.
2. Configuramos los equipos según el ejercicio 2. Los equipos utilizarán boxes de vagrant, en concreto bullseye64. A cada máquina le asignamos un hostname, una IP fija y una provisión donde actualizamos la VM e instalamos las herramientas para usar DNS.

3. Configuramos el named.conf.options de la VM Tierra para que:
    1. No escuche a las direcciones ipv6.
    2. Permita consultas dentro de su misma red.
    3. Permita las consultas recursivas.
    4. Activar DNSSEC
    5.  Asignar la dirección 208.67.222.222 para los reenvíos de consultas.
    
    ![Configuración de Tierra](./images/captura-conf-tierra.png)

4. Configuramos named.conf.local y le damos autoridad sobre la zona directa e inversa.

![Configuración de named.conf.local en Tierra](./images/captura-conf-local-tierra.png)


5. Creamos y configuramos db.sistema.test y db.192 asignando así una configuración de las zonas en cada archivo. En estas configuracione asignamos puertos para las distintas conexiones.

![Configuración de db.sistema.test](./images/captura-db-sistema-test.png)

![Configuración de db.192](./images/captura-db-192.png)