# VM-tutorial

En este tutorial vamos a aprender cómo conectarnos a una VM en la nube, en la cual vamos a desarrollar la parte analítica del proyecto. Para ello vamos a completar los siguientes pasos:

1. Instalar VScode
2. Crear Config file
3. Crear conexión a la VM 
4. Agregar los puertos para acceder al Workspace

## 1. Instalar VScode

Instalen la versión de su preferencia de  [VScode](https://code.visualstudio.com/download) e instalen las siguientes extensiones:

![alt text](https://github.com/sebastian2296/VM-tutorial/blob/main/img/VScode_extensions.png)


## 2. Crear config file

Vamos a crear un config file para hacer la conexión por medio de SSH. Para esto:

* Creen la carpeta *ds4a-code* en su escritorio y guarden la llave que les voy a compartir en esta misma.

* Abran la terminal de VScode

![alt text](sebastian2296/https://github.com/sebastian2296/VM-tutorial/blob/main/img/VScode_terminal.png)

* Creamos la carpeta en la que este archivo va a vivir con el siguiente comando: `mkdir .ssh` . Si les aparece que ya existe, no hay problema. Si no les aparece nada, tampoco hay problema :D 

*Creamos el archivo : 

```sh
cd .ssh/ 
touch config
code .
```

Entramos al archivo config y agregamos la siguiente info:

```
Host ds4a
  Hostname 20.232.203.56
  User azureuser
  IdentityFile C:\Users\<SU-USUARIO>\Desktop\ds4a-code\ds4a-vm_key.pem
```

Guardamos y estamos listos para probar la conexión.
## 3. Creamos la conexión 

Vamos a la ventana de VScode y creamos la conexión a la VM:

* Damos click sobre el ícono verde en la parte inferior izquierda y creamos la conexión con la opicón **Connect to Host**.

![alt text](https://github.com/sebastian2296/VM-tutorial/blob/main/img/ssh_conn.PNG)

* En este punto deben encontrar el path al archivo config que creamos en el paso 3. Seleccionan ds4a y esperan a que se genere la conexión. En última instancia,
deberían ver algo como:

![alt text](https://github.com/sebastian2296/VM-tutorial/blob/main/img/VScode_vm_conn.png)

## 4. Exportar puertos

En este punto debemos exportar los puertos 8888 y 8550 para poder acceder al workspace de JupyterHub/C1, para esto:

* Vamos a la pestaña ports en la ventana de VScode en la que tenemos la conexión a la VM y agregamos los puertos clickeando en **Add port** y listo. 

![alt text](https://github.com/sebastian2296/VM-tutorial/blob/main/img/VScode_ports.png)
