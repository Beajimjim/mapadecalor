# Calendario de Reservas con Flask

## Descripción

Este proyecto implementa una aplicación web con **Flask** que permite visualizar un **calendario anual de reservas**. Genera datos simulados de reservas y los representa en una interfaz web con colores que indican la cantidad de reservas por día.

## Características

- Generación de reservas aleatorias para un año completo.
- Exclusión de reservas los días lunes.
- API para obtener datos de reservas en formato JSON.
- Visualización en un calendario interactivo en la web.
- Uso de Flask para el backend y JavaScript para la renderización del calendario.

## Instalación

### Requisitos

- Python 3.x
- Flask

### Pasos de instalación

1. Clonar el repositorio:

   ```
   git clone <URL_DEL_REPOSITORIO>
   cd <NOMBRE_DEL_REPOSITORIO>
   ```

2. Crear un entorno virtual (opcional pero recomendado):

   ```
   python -m venv venv
   source venv/bin/activate  # En Windows usar: venv\Scripts\activate
   ```

3. Instalar dependencias:

   ```
   pip install flask
   ```

## Uso

1. Ejecutar la aplicación:

   ```
   python app.py
   ```

2. Abrir un navegador y acceder a:

   ```
   http://127.0.0.1:5000/flask/calendario
   ```

## Estructura del Proyecto

```
/<NOMBRE_DEL_REPOSITORIO>
│── app.py               # Backend en Flask
│── calendario.html      # Interfaz web del calendario
│── templates/           # Carpeta para archivos HTML (si es necesario)
│── static/              # Archivos estáticos (CSS, JS)
│── README.md            # Este archivo
```

## API

### Obtener reservas por día

**Endpoint:**  
`GET /flask/reservas_calendario`

**Respuesta:**

```json
[
  {
    "fecha": "YYYY-MM-DD",
    "cantidad": N
  },
  ...
]
```

## Contribución

1. Hacer un fork del repositorio.
2. Crear una rama con los cambios:

   ```
   git checkout -b mi-rama
   ```

3. Confirmar y subir cambios:

   ```
   git commit -m "Descripción de cambios"
   git push origin mi-rama
   ```

4. Abrir un **Pull Request**.

## Licencia

Este proyecto se distribuye bajo la licencia **MIT**.
