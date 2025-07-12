# Pico y Placa - Consulta de Circulación Vehicular

## Descripción

Aplicación web fullstack que permite consultar si un vehículo puede circular en una fecha y hora determinadas, según la normativa de Pico y Placa. Incluye validaciones completas de datos y una opción especial para personas mayores de edad con permiso, que pueden circular sin restricciones.

---

## Arquitectura

![Arquitectura](./docs/blueprint.png)

- **Frontend:** Angular (formulario interactivo, validaciones, consumo de API REST)
- **Backend:** Spring Boot (Java) - expone API REST, toda la lógica y validaciones
- **Comunicación:** HTTP/REST, JSON

---

## Requisitos

- Node.js 18+  
- Angular CLI  
- Java 17+  
- Maven 3.8+

---

## Instalación y Ejecución

### **Backend (Spring Boot)**

1. Ve a la carpeta del backend
2. Instala dependencias y compila:
    ```bash
    ./mvnw clean package
    ```
    o, si tienes Maven global:
    ```bash
    mvn clean package
    ```
3. Corre la aplicación:
    ```bash
    java -jar target/picoyplaca_backend-*.jar
    ```
    - Por defecto escucha en [http://localhost:8080/](http://localhost:8080/)

---

### **Frontend (Angular)**

1. Ve a la carpeta del frontend
2. Instala dependencias:
    ```bash
    npm install
    ```
3. Levanta la app:
    ```bash
    ng serve --open
    ```
    - Se abre en [http://localhost:4200/](http://localhost:4200/)
    - El backend debe estar activo para hacer consultas

---

## Uso

- Ingresa la placa, fecha y hora a consultar.
- Puedes marcar la opción "**¿Es mayor de edad y tiene permiso especial para circular?**" para simular una exención.
- Haz click en **Consultar**.
- El sistema te indicará si el vehículo puede circular o no, según las reglas vigentes.

---

## Validaciones

- **Placa:** 3 letras seguidas de 3 o 4 números (ejemplo: ABC123 o ABC1234)
- **Fecha:** No permite fechas anteriores a la actual
- **Hora:** Si se elige el día de hoy, la hora debe ser igual o posterior a la actual
- **Mayor de edad con permiso:** Si el check está marcado, puede circular siempre, sin restricción

---

## Estructura del Proyecto

