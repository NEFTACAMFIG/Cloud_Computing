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
