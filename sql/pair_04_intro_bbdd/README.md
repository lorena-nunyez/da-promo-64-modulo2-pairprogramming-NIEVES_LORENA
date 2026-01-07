# Pair 04 — Intro a Bases de Datos (Diseño + Normalización)

Este pair corresponde a la introducción a bases de datos relacionales: diseño conceptual, relaciones (cardinalidades), claves primarias/foráneas, diagramas ER con MySQL Workbench y un bonus de normalización hasta 3FN.

---

## Estructura de esta carpeta

```text
sql/pair_04_intro_bbdd/
├── README.md
├── biblioteca_modelo.md
├── conferencias_modelo.md
├── bonus_normalizacion.md
├── biblioteca.mwb               
├── biblioteca_diagrama.png     
├── conferencias.mwb             
└── conferencias_diagrama.png     
```

### 1) Diseño de una base de datos (Biblioteca)

Objetivo

Diseñar un sistema para gestionar:

- Libros

- Autores

- Usuarios

- Préstamos

📌 Entregable: modelo conceptual + relaciones + claves + diagrama ER en Workbench.

➡️ Detalle completo del diseño: biblioteca_modelo.md
➡️ Diagrama ER: biblioteca_diagrama.png (y archivo fuente biblioteca.mwb)

### 2) Diseño de Bases de Datos Asistido por IA (Conferencias)

Objetivo

Diseñar una base de datos completa para conferencias académicas, utilizando Ollama como apoyo para:

Identificar tablas necesarias (incluyendo intermedias N:M)

Validar normalización (3FN)

Proponer tipos de datos y constraints

Generar SQL (en el siguiente pair)

📌 Entregable: modelo conceptual + tablas finales + decisiones de normalización.

➡️ Detalle completo del diseño: conferencias_modelo.md
➡️ Diagrama ER: conferencias_diagrama.png (y archivo fuente conferencias.mwb)

### 3) Bonus — Normalización a 3FN (sin entrega obligatoria)

Se parte de una tabla no normalizada (alumnas + asignaturas + nota) y se propone un diseño en 3FN.

➡️ Propuesta final: bonus_normalizacion.md

Herramientas usadas

MySQL Workbench (EER Diagram / Forward Engineer)

MySQL 8.x

Ollama + mistral:7b (asistencia en el diseño del esquema de conferencias)
