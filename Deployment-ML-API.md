# Creación de API para servir modelo de Machine Learning #

1. Lanzar una instancia en AWS
2. Si se creo una llave darle los permisos y conectarse con el comando ssh
3. Preparar el setup desde la terminal
  - 3.1 Actualizar la maquina `sudo apt-get update`
  - 3.2 Instalar PIP `sudo apt install python3-pip`
  - 3.3 Realizar nuevamente un Update
4. Instalar el venv `sudo apt-get install python3-venv`
5. Crear ambiente virtual
  - 5.1 Crear carpeta para los ambientes virtuales `mkdir “Nombre del proyecto”`
  - 5.2 Crear otra carpeta para el proyecto de las APIS `mkdir “Nombre del proyecto”`
    - 5.2.1 Aquí se crea el ambiente virtual `python3 -m venv “Nombre de la API”`
   
## UNIR PYCHARM CON EL AMBIENTE VIRTUAL CREADO EN LA MAQUINA VIRTUAL ##

1. Generar un nuevo proyecto en Pycharm
  - 1.1 Eliminar el ambiente virtual que se creo
  - 1.2 Ir a `settings` y después `Project`
  - 1.3 Ir a `Python Interprete` y dar click en `Agregar Interprete`, dar click en `SSH`
  - 1.4 Dar el Host y el username Host: DNS Publico Username: Ubuntu
  - 1.5 Indicar como conexión nueva y dar en `NEXT`
  - 1.6 Validar con una llave, seleccionar la llave generada en AWS, DAR `NEXT`
  - 1.7 Escoger una locación, el interprete y el folder en donde se va a sincronizar(Todo esto en la maquina virtual)
  - 1.8 Dar en `crear`, `apply` y `OK`

2. Instalar el PYENV `sudo apt install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev`
  - 2.1 `sudo apt-get install openssl`

3. `git clone https://github.com/pyenv/pyenv.git ~/.pyenv`
  - 3.1 `export PYENV_ROOT=“$HOME/.pyenv”`
  - 3.2 `export PATH=“$PYENV_ROOT/bin:$PATH”`
  - 3.3 `eval “$(pyenv init --path)”`
  - 3.4 `source ~/.bashrc and pyenv --version`

4. Activar el ambiente virtual
  - 4.1  `source Nombre del ambiente/bin/activate`

5. Instalar librerías y paquetes
  - 6.1 `pip install pandas`
  - 6.2 `pip install -U scikit-learn`
  - 6.3 `pip install flask`
  - 6.4 `pip install pickle5`
  - 6.5 `pip install mlflow[extras]`
