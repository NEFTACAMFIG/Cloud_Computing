Creación de API para servir modelo de Machine Learning

1. Lanzar una instancia en AWS 
2. Si se creo una llave darle los permisos y conectarse con el comando ssh
3. Preparar el setup desde la terminal
	3.1 Actualizar la maquina sudo apt-get update
	3.2 Instalar PIP sudo apt install python3-pip
	3.3 Realizar nuevamente un Update
4. Instalar el venv sudo apt-get install python3-venv
5. Crear ambiente virtual
	5.1 Crear carpeta para los ambientes virtuales mkdir “Nombre del proyecto”
	5.2 Crear otra carpeta para el proyecto de las APIS mkdir “Nombre del proyecto”
		5.2.1 Aquí se crea el ambiente virtual python3 -m venv “Nombre de la API”

UNIR PYCHARM CON EL AMBIENTE VIRTUAL CREADO EN LA MAQUINA VIRTUAL
I. Generar un nuevo proyecto en Pycharm
	I.I Eliminar el ambiente virtual que se creo
	I.II Ir a settings y después Project
	I.III Ir a Python Interprete y dar click en Agregar Interprete, dar click en SSH
	I.IV Dar el Host y el username Host: DNS Publico Username: Ubuntu
	I.V Indicar como conexión nueva y dar en NEXT
	I.VI Validar con una llave, seleccionar la llave generada en AWS, DAR NEXT
	I.VII Escoger una locación, el interprete y el folder en donde se va a sincronizar (Todo esto en la maquina virtual)
	I.VIII Dar en crear, apply y OK
6. Instalar el PYENV sudo apt install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
	6.1 sudo apt-get install openssl
7. git clone https://github.com/pyenv/pyenv.git ~/.pyenv 
	7.1 export PYENV_ROOT=“$HOME/.pyenv”
	7.2 export PATH=“$PYENV_ROOT/bin:$PATH”
	7.3 eval “$(pyenv init --path)”
	7.4 source ~/.bashrc and pyenv --version
8. Activar el ambiente virtual
	8.1  source Nombre del ambiente/bin/activate
9. Instalar librerías y paquetes
	9.1 pip install pandas
	9.2 pip install -U scikit-learn
	9.3 pip install flask
	9.4 pip install pickle5
	9.5 pip install mlflow[extras]
10. Escribir el código en un archivo .py de nuestro modelo
11. Crear archivo tipo YAML
	11.1 Nombre.yaml
	11.2 Especificar las condiciones con las que se crearon el experimento

		python:”3.10” ————> Versión de Python
		build_dependencies:
			-pip
		dependencies:
			- mlflow==2.1.2 ————> Versión de MLFLow
			- scikit-learn==1.1.1
			- pandas==1.5.3

	11.3 Guardar y cerrar el archivo
12. Crear archivo tipo TEXT
	12.1 Nombre del archivo: MLproject

		name: “Nombre del Proyecto”
		python_env: “Nombre del archivo.yaml”
		entry_points:
			main:
				parameters:
					C: {type: float, default: 1.0}
					max_iter: {type: int, default: 100}
				command:
					python3 Nombre del archivo.PY --C={C} --max_iter={max_iter}


13. Correr la interfaz
	13.1 mlflow run . -P C =0.05
	13.2 mlflow ui --host 0.0.0.0
14. Acceder al Dashboard de MLFlow
	14. DNS Publica:5000
15. Para servir el modelo
	15.1 Una vez checado que el modelo corre, cerrar la interfaz y escribir el siguiente código
	15.2 mlflow models serve -m “DNS generada por mlflow a partir de HOME” -p 1234 -h 0.0.0.0
16 Ya se pueden realizar peticiones del tipo POST
