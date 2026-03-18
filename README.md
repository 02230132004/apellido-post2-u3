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


