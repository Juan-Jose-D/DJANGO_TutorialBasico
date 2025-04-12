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


**Nota importante:** Django requiere **Python 3.8 o superior**. Para usuarios de Linux/macOS donde el comando anterior no funcione, probamos con:

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

Django es un framework de desarrollo web de código abierto, escrito en Python, que respeta el patrón de diseño conocido como modelo–vista–controlador.

Con este podemos desarrollar aplicaciones tanto de frontend como de backend de manera mas sencilla.

(Es similar a Spring en Java)

**Instalación de Django**

Si tenemos python la instalación de Django es muy sencilla, lo único que debemos hacer es abrir una terminal y ejecutar el comando:

`python -m pip install Django`

*pip* normalmente se instala cuando instalamos python, pero en caso de que salga un error nos podemos dirigirnos a la siguiente página para descargarlo manualmente y volvemos a intentar la instalación del django:

https://pip.pypa.io/en/stable/installation/


Una vez terminado todo este proceso de instalación de las herramientas que necesitamos, podemos empezar a crear nuestro primer proyecto.

## Proyecto usando Poetry y Django

### Paso 1: Configurar el proyecto con Poetry

1. Abrir una terminal

```bash
# Creamos el directorio del proyecto
mkdir tuto

# Nos movemos al directorio recién creado
cd tuto

# Inicializamos Poetry
poetry init

```


