# apellido-post2-u3

# Aplicación de Tareas - Post-Contenido 2  
**Unidad 3: Arquitectura de Aplicaciones Móviles**  
Ingeniería de Sistemas – Universidad de Santander (UDES) – 2026

## Descripción del proyecto

Esta aplicación es una lista de tareas sencilla desarrollada en **Jetpack Compose** que fue refactorizada desde una arquitectura **MVVM básica con Hilt** (Post-Contenido 1) hacia **Clean Architecture** con las siguientes características principales:

- Separación estricta en **tres capas**:
  - **Domain**: contiene la lógica de negocio pura (modelo `Task`, interfaz `TaskRepository`, **Use Case** `GetPendingTasksUseCase`). **Sin dependencias de Android**.
  - **Data**: implementación concreta del repositorio (`InMemoryTaskRepository` con datos en memoria).
  - **Presentation**: capa de UI (Composable) y ViewModel (`TaskViewModel`).
- Uso de **Koin** como framework de inyección de dependencias (reemplaza completamente Hilt).
- Un **Use Case** dedicado (`GetPendingTasksUseCase`) que encapsula la regla de negocio:  
  → Mostrar **solo tareas pendientes**  
  → Ordenadas por **ID descendente** (las más recientes primero)
- Tests unitarios del Use Case con **JUnit** + **kotlinx-coroutines-test**.

## Arquitectura implementada (Clean Architecture)

<img width="486" height="541" alt="image" src="https://github.com/user-attachments/assets/42f60630-a83f-4e10-9a95-7db820306c0f" />


**Regla de dependencias respetada**:  
La capa **domain** NO depende de ninguna otra capa ni del SDK de Android.

## Capturas de los checkpoints obligatorios

### Checkpoint 1 – Capa domain sin imports de Android

Búsqueda en todo el paquete `domain` de la cadena `"import android"`:  
**Resultado: 0 coincidencias**

<img width="1111" height="1030" alt="image" src="https://github.com/user-attachments/assets/1311977c-9f7f-4d21-ae91-9ba07d27fddf" />


### Checkpoint 2 – Solo se muestran tareas pendientes

La aplicación muestra únicamente las tareas **no completadas** (4 tareas en total).  
La tarea "Leer documentación de Koin DSL" está marcada como completada y **no aparece** en la lista.

<img width="1919" height="1077" alt="image" src="https://github.com/user-attachments/assets/584d483f-65eb-447d-b367-7832bcdb4b3f" />


### Checkpoint 3 – Tests unitarios pasan

Ejecución de `./gradlew test` → **BUILD SUCCESSFUL**  
Ambos tests del `GetPendingTasksUseCase` pasan correctamente.

![Checkpoint 3 - Tests pasando](https://i.imgur.com/XXXXXXXXXXXXXXXX.png)  
*(reemplaza con tu captura real)*

## Commits principales (extracto)

- `Agrega estructura de paquetes Clean Architecture (domain, data, presentation)`
- `Implementa GetPendingTasksUseCase y migra repositorio a InMemoryTaskRepository`
- `Reemplaza Hilt por Koin + actualiza ViewModel y MyApp`
- `Agrega tests unitarios del Use Case`
- `Documenta README con checkpoints y descripción de arquitectura`

## Tecnologías utilizadas

- Kotlin + Jetpack Compose
- Clean Architecture
- Koin (DI)
- StateFlow + Coroutines
- JUnit 4 + kotlinx-coroutines-test




