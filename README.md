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
-----



# Explicación del Sistema de Reservas con Flask y JavaScript

## **Explicación General**
Este sistema consta de dos archivos principales:

1. **`app.py`** → Un servidor Flask que maneja rutas para mostrar el calendario y proporcionar datos de reservas.
2. **`calendario.html`** → Un archivo HTML con JavaScript que genera dinámicamente un calendario anual y visualiza las reservas de cada día.

---

## **`app.py` (Servidor Flask)**
### **Inicio del servidor**
- Se utiliza **Flask** para crear un servidor web.
- La aplicación se expone en la URL `/flask`.

### **Generación de reservas**
- Se simulan reservas aleatorias para todo el año actual.
- Cada reserva se almacena con una fecha específica.
- Se evitan los lunes al generar reservas.

### **Agrupación de reservas**
- Se contabiliza cuántas reservas hay por cada día del año.
- Los datos se organizan en un formato de lista con fecha y cantidad.

### **Rutas de la API**
- **`/flask/reservas_calendario`** → Devuelve los datos de reservas en formato JSON.
- **`/flask/calendario`** → Carga la página `calendario.html`.

### **Ejecución del servidor**
- El servidor Flask inicia en el puerto **5000** con modo **debug activado**.

---

## **`calendario.html` (Interfaz Web)**
### **Estructura HTML**
- Un `div` con el ID **"calendario"** actúa como contenedor del calendario.
- Se carga el calendario dinámicamente con JavaScript.

### **Estilos CSS**
- Se utiliza **flexbox** para organizar los meses en filas y columnas.
- Cada mes tiene un **ancho fijo** y está dentro de un `div`.
- Se definen estilos responsivos para adaptar el diseño en dispositivos pequeños.

### **Carga de Datos desde la API**
- Se obtiene la lista de reservas haciendo una petición **fetch()** a `/flask/reservas_calendario`.
- Se almacena la cantidad de reservas por cada fecha.

### **Construcción del Calendario**
- Se crean **12 tablas** (una por mes).
- Cada tabla tiene **7 columnas** (días de la semana) y **hasta 6 filas**.
- Se ajusta el calendario para que el **lunes sea el primer día de la semana**.
- Se colorean los días dependiendo de la cantidad de reservas:
  - **Rojo intenso** = muchas reservas.
  - **Blanco** = sin reservas.
  - **Gradientes** entre rojo y blanco según la cantidad de reservas.

---

## **Flujo Completo**
1. **El servidor Flask inicia y genera datos de reservas aleatorios.**
2. **Cuando el usuario accede a `/flask/calendario`, se muestra `calendario.html`.**
3. **El código JavaScript dentro de `calendario.html` hace una petición a la API `/flask/reservas_calendario` para obtener las reservas.**
4. **El JavaScript genera un calendario dinámico y colorea los días según las reservas.**
5. **El usuario ve el calendario actualizado con los datos de reservas.**

---

## **Resumen Final**
Este código genera un **calendario dinámico de reservas** usando Flask en el backend y JavaScript en el frontend. Los datos se generan aleatoriamente en el servidor y se visualizan en la interfaz web con un sistema de colores. 🚀

