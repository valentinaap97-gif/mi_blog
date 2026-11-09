# ☕ Café de Especialidad

Blog web sobre café de especialidad, desarrollado con Django. Los usuarios registrados pueden publicar reseñas y notas sobre calidad de café, con imagen opcional, y cualquier visitante puede leerlas.

## Tecnologías utilizadas

- Python
- Django
- SQLite
- Pillow (manejo de imágenes)
- python-decouple (variables de entorno)
- Bootstrap 5 (estilos, cargado desde CDN)

## Funcionalidades principales

- Listado de posts con paginación y detalle de cada post.
- Crear, editar y eliminar posts desde la interfaz web.
- Carga de imagen en los posts (opcional: si un post no tiene imagen, la página funciona igual).
- Registro de usuarios, inicio y cierre de sesión.
- Rutas protegidas: crear, editar y eliminar posts requieren sesión iniciada, y solo el autor puede modificar o borrar sus propios posts.
- Panel de administración de Django.

## Instalación

Requisitos: Python 3.12 o superior y Git.

1. Clonar el repositorio:

```
git clone https://github.com/valentinaap97-gif/mi_blog.git
cd mi_blog
```

2. Crear y activar el entorno virtual (Windows, PowerShell):

```
python -m venv venv
venv\Scripts\Activate.ps1
```

En Mac o Linux:

```
python3 -m venv venv
source venv/bin/activate
```

3. Instalar las dependencias:

```
pip install -r requirements.txt
```

4. Crear el archivo `.env` a partir del ejemplo (en Windows: `copy .env.example .env`; en Mac o Linux: `cp .env.example .env`) y reemplazar el valor de `SECRET_KEY` por una clave propia. Se puede generar con:

```
python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"
```

5. Aplicar las migraciones (crea la base de datos SQLite):

```
python manage.py migrate
```

6. Iniciar el servidor:

```
python manage.py runserver
```

La aplicación queda disponible en http://127.0.0.1:8000/

## Cómo probar el proyecto desde cero

El repositorio no incluye la base de datos (`db.sqlite3`) ni la carpeta `media/`, por lo que se parte de un blog vacío:

1. Entrar a `/registro/` y crear un usuario.
2. Iniciar sesión en `/login/`.
3. Usar el botón **Nuevo post** para crear publicaciones, con o sin imagen. Las imágenes subidas se guardan en `media/`, que se crea automáticamente.

## Panel de administración

Para acceder al panel (`/admin/`) hay que crear un superusuario:

```
python manage.py createsuperuser
```

## Estructura del proyecto

```
mi_blog/
├── blog/          # app principal (modelos, vistas, urls, templates)
├── mi_blog/       # configuración del proyecto
├── templates/     # base.html y templates de registro/login
├── .env.example   # variables de entorno necesarias (sin valores reales)
├── manage.py
└── requirements.txt
```

## Autora

Valentina Agüero Pinto