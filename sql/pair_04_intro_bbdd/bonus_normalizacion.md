# Bonus — Normalización a 3FN

Tabla original (no normalizada):

- id_alumna, nombre, dirección, id_asignatura, asignatura, nota

## Problema

- Se repite nombre y dirección por cada asignatura de la misma alumna.
- Se repite el nombre de la asignatura por cada alumna.
- La nota pertenece a la relación alumna-asignatura.

---

## Propuesta en 3FN

### 1) ALUMNAS

- **id_alumna** (PK)
- nombre
- direccion

### 2) ASIGNATURAS

- **id_asignatura** (PK)
- asignatura

### 3) NOTAS (o alumnas_asignaturas)

- **id_alumna** (FK → alumnas.id_alumna)
- **id_asignatura** (FK → asignaturas.id_asignatura)
- nota
- **PK compuesta:** (id_alumna, id_asignatura)

---

## Por qué esto es 3FN

- Cada tabla almacena un único “tipo” de entidad.
- Todas las columnas dependen de su clave primaria.
- No hay dependencias parciales ni transitivas.
