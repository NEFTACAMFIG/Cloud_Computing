# Creación de APIS usando maquina virtual

1. Lanzar una instancia en AWS 
2. Si se creo una llave darle los permisos y conectarse con el comando ssh
3. Preparar el setup desde la terminal

    *  3.1 Actualizar la maquina `sudo apt-get update`
    *  3.2 Instalar PIP `sudo apt install python3-pip`
    *  3.3 Realizar nuevamente un Update `sudo apt-get update`	

4. Instalar el venv `sudo apt-get install python3-venv`
5. Crear ambiente virtual
	- 5.1 Crear carpeta para los ambientes virtuales `mkdir “Nombre del proyecto”`
	- 5.2 Crear otra carpeta para el proyecto de las APIS `mkdir “Nombre del proyecto”`
	  - 5.2.1 Aquí se crea el ambiente virtual `python3 -m venv “Nombre de la API”`	
		

## UNIR PYCHARM CON EL AMBIENTE VIRTUAL CREADO EN LA MAQUINA VIRTUAL ##

6. Generar un nuevo proyecto en Pycharm
	- 6.1 Eliminar el ambiente virtual que se creo
	- 6.2 Ir a settings y después Project
	- 6.3 Ir a Python Interprete y dar click en Agregar Interprete, dar click en SSH
	- 6.4 Dar el Host y el username Host: DNS Publico Username: Ubuntu
	- 6.5 Indicar como conexión nueva y dar en NEXT
	- 6.6 Validar con una llave, seleccionar la llave generada en AWS, DAR NEXT
	- 6.7 Escoger una locación, el interprete y el folder en donde se va a sincronizar (Todo esto en la maquina virtual)
	- 6.8 Dar en crear, apply y OK

7. Activar el ambiente virtual
	6.1 Nombre del ambiente/bin/activate
7. Instalar librerías y paquetes
	7.1 pip install pandas
	7.2 pip install -U scikit-learn
	7.3 pip install flask
8. Crear archivo en Python para que se ejecute el API
9. Correr la api desde la terminal
	9.1 python3 Nombre de la API.py
10. La API se puede correr abriendo el navegador y usando la DNS Pública: Puerto/? Entrada_1= Valor & Entrada_2= Valor 

