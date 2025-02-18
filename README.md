Calendario de Reservas con Flask
Descripción
Este proyecto implementa una aplicación web con Flask que permite visualizar un calendario anual de reservas. Genera datos simulados de reservas y los representa en una interfaz web con colores que indican la cantidad de reservas por día.

Características
Generación de reservas aleatorias para un año completo.
Exclusión de reservas los días lunes.
API para obtener datos de reservas en formato JSON.
Visualización en un calendario interactivo en la web.
Uso de Flask para el backend y JavaScript para la renderización del calendario.
Instalación
Requisitos
Python 3.x
Flask
Pasos de instalación
Clonar el repositorio:

bash
Copiar
Editar
git clone <URL_DEL_REPOSITORIO>
cd <NOMBRE_DEL_REPOSITORIO>
Crear un entorno virtual (opcional pero recomendado):

bash
Copiar
Editar
python -m venv venv
source venv/bin/activate  # En Windows usar: venv\Scripts\activate
Instalar dependencias:

nginx
Copiar
Editar
pip install flask
Uso
Ejecutar la aplicación:

nginx
Copiar
Editar
python app.py
Abrir un navegador y acceder a:

arduino
Copiar
Editar
http://127.0.0.1:5000/flask/calendario
Estructura del Proyecto
php
Copiar
Editar
/<NOMBRE_DEL_REPOSITORIO>
│── app.py               # Backend en Flask
│── calendario.html      # Interfaz web del calendario
│── templates/           # Carpeta para archivos HTML (si es necesario)
│── static/              # Archivos estáticos (CSS, JS)
│── README.md            # Este archivo
API
Obtener reservas por día
Endpoint:
GET /flask/reservas_calendario

Respuesta:

json
Copiar
Editar
[
  {
    "fecha": "YYYY-MM-DD",
    "cantidad": N
  },
  ...
]
