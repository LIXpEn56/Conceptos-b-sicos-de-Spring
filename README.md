
UNIVERSIDAD AUTÓNOMA DE CAMPECHE

	FACULTAD DE INGENIERÍA

	INGENIERO EN SISTEMAS COMPUTACIONALES





ALUMNO(A): 			          SANCHEZ RAMIREZ SANDRA LIZETTE

SEMESTRE: 			          8VO 


UNIDAD DE APRENDIZAJE:	  TEMAS SELECTOS DE PROGRAMACIÓN


PROFESOR  :   JOSE AGUILAR CANEPA


# Conceptos-b-sicos-de-Spring
Aplicación simple en Spring que implemente las siguientes características

# Aplicación de Censura de Mensajes con Spring Boot y AOP

Esta es una aplicación simple construida con **Spring Boot** que permite al usuario ingresar mensajes desde la terminal y los filtra automáticamente detectando y reemplazando palabras prohibidas. Utiliza programación orientada a aspectos (**AOP**) para interceptar los mensajes y aplicar la censura de forma transparente.

---

## Características

- Ingreso de mensajes desde consola (terminal).
- Lista configurable de palabras prohibidas.
- Sustitución de palabras por caracteres especiales (`!#?%@`).
- Mensaje de advertencia si el mensaje contiene más de 3 palabras prohibidas.
- Implementación modular con **Spring AOP**.

---

## Arquitectura y Componentes

### 1. `Application.java` – Clase principal

Arranca la aplicación y abre un bucle que permite ingresar mensajes por consola. Cada mensaje se envía al servicio `MessageService` para ser procesado.

### 2. `MessageService.java` – Servicio de mensajes

Contiene el método `processMessage(...)`, que será interceptado por un aspecto para aplicar la lógica de censura.

### 3. `AppConfig.java` – Lista de palabras prohibidas

###4 CensorshipAspect.java – Aspecto de censura (AOP)
- Reemplaza palabras prohibidas con caracteres (!#?%@).
- Si hay más de 3 coincidencias, devuelve un mensaje de advertencia.
- Si no, continúa con el flujo del método censurando las palabras.

Define un bean de configuración que contiene una lista de palabras consideradas "prohibidas". Esta lista se puede modificar fácilmente.
