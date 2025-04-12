# Tutorial Básico DJANGO

## Python

**Verificar instalación de Python**

Para comenzar, verificaremos si tenemos Python instalado en nuestro sistema.

1. Abrimos la terminal/consola:

- Windows: Presionamos Windows + R, escribimos cmd y presionamos Enter
- macOS/Linux: Abrimos la aplicación Terminal desde el sistema

2. Ejecutamos el comando de verificación:

` python --version `

- Si tenemos Python instalado, veremos la versión
- Si obtenemos un error, significa que no está instalado


**Nota importante:** Django requiere **Python 3.8 o superior**. 

Para usuarios de Linux/macOS donde el comando anterior no funcione, probamos con:

` python3 --version `

**Instalación de Python**

Si no contamos con Python instalado descargamos la última versión en esta página:

- https://www.python.org/downloads/
- Descargamos la última versión estable
- Seguimos el asistente de instalación
- Para Windows: Marcamos la opción "Add Python to PATH" durante la instalación

## Poetry - Gestión de dependencias

**¿Qué es Poetry?**

Poetry es un gestor de paquetes y dependencias para Python que:

- Maneja entornos virtuales automáticamente.
- Simplifica la gestión de bibliotecas
- Permite replicar entornos de desarrollo fácilmente

(Es similar a Maven/Gradle en Java o npm en JavaScript)

**Instalación de Poetry**

Seguimos estos pasos para instalar Poetry:

1. Abrimos una nueva terminal
2. Ejecutamos el comando oficial (Windows/macOS/Linux):

`curl -sSL https://install.python-poetry.org | python3 - `

3. Esperamos a que finalice el proceso de instalación

Si estamos trabajando en un Windows el instalador debería añadirlo automáticamente al PATH.

Para verificar abre una nueva terminal, y escribimos el comando

`poetry --version`

Si aparece la versión instalada (ej: Poetry 1.7.0), todo está correcto.

En caso contrario nos dirigimos a la página de instalación de Poetry y seguimos los pasos para añadirlo al PATH manualmente.

https://python-poetry.org/docs/#installing-with-the-official-installer


## Django

**¿Qué es Django?**

Django es un framework web de código abierto escrito en Python que sigue el patrón MTV (Modelo-Template-Vista), una variante especializada del clásico MVC (Modelo-Vista-Controlador). Permite desarrollar:

- Aplicaciones backend robustas.
- APIs RESTful.
- Sistemas de gestión de contenido.
- Soluciones full-stack (combinando su sistema de templates).



## Proyecto usando Poetry y Django

### Paso 1: Configurar el proyecto con Poetry

1. Abrir una terminal

```bash
# Creamos el directorio del proyecto
mkdir tutorial

# Nos movemos al directorio recién creado
cd tutorial

# Inicializamos Poetry
poetry init 
```

Cuando inicializamos el Poetry nos da la opción de darle un nombre al paquete del proyecto, la versión, la descripción, el autor, la licencia y otras configuraciones.Todas estas son opcionales, entonces en caso de no querer configurarlas solo damos Enter y se pondrán las que vienen por defecto, estas las podremos cambiar después, entonces no hay riesgo.

En la parte que nos dice si queremos deifinir las dependencias principales interactivamente daremos que no, por ahora y confirmamos la generación del proyecto.

<hr>

Una vez hecho esto veremos en el directorio en el que hicimos el init un archivo llamado *"pyproject.toml"*

El .toml es un archivo de configuración utilizado por herramientas de empaquetado, en este podremos cambiar algunas configuraciones de nuestro proyecto, así como agregar y manejar las dependencias (Es como el equivalente al pom de maven). Sirve también como configurador de entornos virtuales y definidor de metadatos del proyecto


### Paso 2: Instalar Django en el entorno virtual

Para comenzar a usar poetry vamos a activar el entorno virtual de poetry.

Un entorno virtual es un espacio aislado dentro del sistema donde podemos instalar paquetes específicos de Python sin afectar el resto del sistema o a otros proyectos.

Por ejemplo podemos tener dos proyectos, uno que use la versión Django 4.2 y otro Django 3.2 y va a funcionar correctamente.

Para activar el entorno virtual ponemos el siguiente comando en nuestra terminal, en la carpeta donde tengamos el .toml:

```bash
# Añadimos un plugin para activación automática de la shell
poetry self add poetry-plugin-shell

# Y activamos el entorno virtual
poetry shell
```
Ahora los paquetes que instalemos se instalarán dentro del entorno, no globalmente.

Podemos correr comandos como python, django-admin, manage.py y se usarán dentro de ese entorno.

<hr>

Como dijimos anteriormente poetry nos sirve para manejar nuestras dependencias de manera muy sencilla, sin instalaciones complicadas y manuales, vamos a usarlo por primera vez, abrimos una terminal en la misma carpeta en donde tenemos el .toml y escribimos el comando:

`poetry add django`

Si miramos nuestro archivo .toml veremos que en el apartado de *dependencies* aparecerá django.


### Paso 3: Crear la estructura básica del proyecto Django

Para crear el inicio del scaffolding de nuestro proyecto Django usaremos el siguiente comando:

`django-admin startproject config .`

Esto creará una un archivo **manage.py** y una carpeta config con unos archivos de configuración de Django que explicaremos resumidamente ahora.

![image](https://github.com/user-attachments/assets/db361851-d7cc-49d9-9f5d-9a2be1a4c148)

<hr>

Comenzaremos explicando el archivo **manage.py** 
