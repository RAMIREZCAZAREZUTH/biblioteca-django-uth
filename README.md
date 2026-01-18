# 📚 Sistema de Biblioteca con Django

Este proyecto consiste en el desarrollo de una aplicación web completa para la gestión de una biblioteca. El sistema permite administrar libros, autores, categorías, editoriales y préstamos de los libros a través de un panel de administración y vistas públicas. Fue desarrollado como parte de la práctica de la unidad 1 de la asignatura **Aplicaciones Web Orientadas a Servicios**.

El objetivo principal es implementar un sistema **CRUD completo** (Crear, Leer, Actualizar, Eliminar) junto con un sistema de autenticación, desplegado finalmente en un entorno de producción.

## 🛠️ Tecnologías Utilizadas

* **Lenguaje:** Python 3.10+
* **Framework Web:** Django 4.2
* **Base de Datos:** MySQL Server 8.0+
* **Librerías Adicionales:**
    * `mysqlclient` (Conector de base de datos)
    * `pillow` (Manejo de imágenes)
    * `django-environ` (Manejo de variables de entorno)
* **Frontend:** HTML5, CSS3, Bootstrap 5 (Responsive Design)
* **Control de Versiones:** Git y GitHub
* **Despliegue:** PythonAnywhere

## 🚀 Instrucciones de Instalación

Sigue estos pasos para configurar el entorno de desarrollo localmente:

### 1. Prerrequisitos
Asegúrate de tener instalado:
* Python 3.10 o superior
* MySQL Server
* Git

### 2. Configuración del Entorno
```bash
# Crear directorio del proyecto
mkdir biblioteca_django
cd biblioteca_django```

# Crear entorno virtual
python -m venv venv

# Activar entorno virtual (Windows)
```bash
.\venv\Scripts\Activate ```
# En Mac/Linux usa: ```bash source venv/bin/activate ```

# Instalar dependencias
```bash
pip install Django==4.2 mysqlclient pillow django-environ
```

### 3. Configuración de la Base de Datos (MySQL)
Ingresar a la base de datos y ejecutar

```sql
CREATE DATABASE biblioteca_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'biblioteca_user'@'localhost' IDENTIFIED BY 'Pass123456!';
GRANT ALL PRIVILEGES ON biblioteca_db.* TO 'biblioteca_user'@'localhost';
FLUSH PRIVILEGES;
```

### 4. Configuración del Proyecto
Crea un archivo .env en la raíz del proyecto (junto a manage.py) con el siguiente contenido:
```bash
DB_NAME=biblioteca_db
DB_USER=biblioteca_user
DB_PASSWORD=Pass123456!
DB_HOST=localhost
DB_PORT=3306
SECRET_KEY=Clave secreta
DEBUG=True
```

### 5. Iniciar el Proyecto
# Crear las migraciones
```bash
python manage.py makemigrations
python manage.py migrate
```

# Crear un superusuario para el admin
```bash
python manage.py createsuperuser
```

# Ejecutar el servidor de desarrollo
```bash
python manage.py runserver
```

## Estructura del proyecto
La estructura principal del proyecto se organiza de la siguiente manera:

```bash
biblioteca_django/
│
├── biblioteca_project/      # Configuración principal del proyecto (settings, urls, wsgi)
│
├── libros/                  # Aplicación principal del sistema
│   ├── migrations/          # Archivos de migración de la BD
│   ├── admin.py             # Configuración del panel de administración
│   ├── apps.py              # Configuración de la app
│   ├── models.py            # Definición de modelos de datos
│   ├── views.py             # Lógica de las vistas
│   └── tests.py             # Pruebas unitarias
│
├── media/                   # Archivos subidos por el usuario (portadas, fotos autores)
│   ├── autores/
│   └── portadas/
│
├── templates/               # Plantillas HTML
├── .env                     # Variables de entorno (no incluir en repositorios públicos)
├── .gitignore               # Archivos ignorados por Git
├── manage.py                # Utilidad de línea de comandos de Django
└── requirements.txt         # Lista de dependencias del proyecto
```

## Información del autor
### Autor: Ramirez Cazarez Fernando
### Carrera: TSU Desarrollo de Software Multiplataforma
### Grupo: TIDSM 5-1
