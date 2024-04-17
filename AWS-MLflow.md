# Script Using AWS y MLFlow #
1. Levantar instancia en AWS
	- 1.1 Abrir página de AWS
	- 1.2 ir al servicio EC2
	- 1.3 Eliminar instancias en ejecución si hay  alguna corriendo
		- 1.3.1 Ir al estado de la estancia
		- 1.3.2	Terminar estancia

2. Ir a Lanzar Instancia
	- 2.1 Seleccionar sistema operativo Ubuntu ya que es de código abierto
	- 2.2 Seleccionar un nombre para la instancia
	- 2.3 Seleccionar una máquina de acuerdo a nuestras necesidades de procesamiento

3. Generar claves
	- 3.1 Las claves deben ser del tipo RSA y .pem para correrlas en Ubuntu

4. Configuración de redes ( Restricciones dependen de los requerimientos de las empresas)
	- 4.1 Permitir el trafico de HTTPS y permitir el trafico HTTP desde internet
	- 4.2 Dar click al buton de `EDITAR`
		- 4.2.1 Dar click a `AGREGAR REGLA DEL GRUPO DE SEGURIDAD`
		- 4.2.2 Dar de alta los puertos `1234`, `3737`, `5000` y `8787` con Tipo de Origen `CUALQUIER LUGAR`

5. Dar click en `LANZAR INSTANCIA`
   
6. Dar click en botón `VER TODAS LAS INSTANCIAS`
   
7. Abrir la terminal
   
8. Crear o ir a la carpeta en donde se guardaran o se guardaron las claves
	- 8.1 Para copiar la llave en la carpeta se puede utilizar `cp ~/Downloads/“Nombre de la clave”`
	- 8.2 Cambiar los permisos para la clave `chmod 600 “nombre de la clave”`
	- 8.3 Conectarnos a la maquina virtual `ssh -i “Nombre de la clave” username@serverIP`
		- 8.3.1 Dar `YES`

9. Generar el SETUP para la maquina virtual
	- 9.1 Actualizar la maquina `sudo apt-get update`
	- 9.2 Instalar PIP `sudo apt-get -y install python3-pip`
	- 9.3 Se puede utilizar `pip list`  para checar todos los paquetes que se instalaron
   
11. Generar SETUP para trabajar con MLFlow
	10.1 Actualizar antes de instalar cualquier dependencia 
	10.2 Instalar el PYENV sudo apt install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
12. git clone https://github.com/pyenv/pyenv.git ~/.pyenv 
	11.1 export PYENV_ROOT=“$HOME/.pyenv”
	11.2 export PATH=“$PYENV_ROOT/bin:$PATH”
	11.3 source ~/.bashrc and pyenv --version
	*11.4 eval “$(pyenv init --path)”
13. Instalar el VENV
	12.1 Crear carpeta para proyecto mkdir “Nombre de la carpeta”
	12.2 sudo apt install python3.8-venv Checar version de Python
	12.3 python3 -m venv mlflowtrck (mlflowtrck es el nombre del ambiente)
	12.4 Activar el ambiente virtual source “nombre del ambiente”/bin/activate
14. Instalar librerías necesarias para el ambiente virtual
	13.1 pip install pandas
	13.2 pip install -U scikit-learn
	13.3 pip install mlflow[extras]
	13.4 Se puede checar las dependencias instaladas con pip list ! grep “Nombre de la dependencia”
15. Crear script con nano
	14.1 nano “Nombre del archivo”.py 	
		14.1.1 control + O + enter para sobrescribir 
		14.1.2 control + X para salir 
		14.1.3 checar si existe el script con cat “nombre del script”
16. Correr experimentos
17. Abrir la interfaz de MLFlow
	16.1 mlflow ui --host=0.0.0.0
	16.2 Se puede acceder con la DNS Publica:5000
	16.3 control + C para cancelar el experimento
