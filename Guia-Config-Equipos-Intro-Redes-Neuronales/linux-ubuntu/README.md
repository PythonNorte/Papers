# configuración de Equipos GNU/Linux Basados en Debian

Proyecto básico con todos los paquetes necesarios para el taller de **Deep Learning** esta instalación se basa en el uso de *[Keras](https://keras.io/)* junto a la librerías *[tensorflow](https://www.tensorflow.org/)*

## Requerimientos

* GNU/Linux OS (Ubuntu)
* Python 3.5.x+
* Paquetes

## Instalación

### Instalar pip3

    $ sudo apt-get install python3-pip python3-dev  

### Actualizar pip3

    $ pip3 install -U upgrade pip

#### Problemas comunes pip3 no funciona (error import) despues de actaulizar

Puede ocurrir que después de actualizar pip3 el mismo no funcione para corregir el problema modifique el archivo `/usr/bin/pip3` y reemplace el siguiente import:

    from pip import main

por:

    from pip._internal import main

La razón de este problema es muy sencilla el paquete `python-pip` esta muy desactualizado (9.0) y la ultima versión disponible a la fecha es la (18.0) y bueno como el error lo menciona se movió la función main()

### Instalar virtualenv

    $ sudo pip3 install -U virtualenv

### Crear el entorno virtual para trabajar en el taller

Situarnos en el directorio del proyecto y crear el entorno virtual

    $ virtualenv -p python3 env

### Activar el entorno virtual

    $ . env/bin/activate

### instalar dependencias

    $ pip install -r requeriments.txt

## Prueba

Con todo esto ya tendremos listo el entorno de trabajo para probar que todo este funcionando se puede probar el siguiente ejemplo.

    $ python mnist_cnn.py
