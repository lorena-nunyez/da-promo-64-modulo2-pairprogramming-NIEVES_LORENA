# Modelo Conferencias Académicas (Diseño asistido por IA)

## 1. Entidades principales

- Conferencias (nombre, año, ciudad, fecha_inicio, fecha_fin, tema_principal)
- Sesiones (nombre, sala, fecha, hora_inicio, hora_fin)
- Ponencias (titulo, resumen, duracion_minutos, tipo: oral/poster)
- Ponentes (nombre, institucion, pais, email, especialidad)
- Asistentes (nombre, email, institucion, pais, tipo_registro: estudiante/profesional)

---

## 2. Tablas necesarias (incluyendo intermedias)

### Tablas principales (5)

1. conferencias
2. sesiones
3. ponencias
4. ponentes
5. asistentes

### Tablas intermedias (2)

1. ponencias_ponentes  
   - Resuelve la relación N:M entre ponencias y ponentes (coautores)

2. inscripciones  
   - Resuelve la relación N:M entre asistentes y conferencias
   - Incluye atributo extra: fecha_inscripcion

---

## 3. Relaciones y cardinalidades

- Una conferencia → muchas sesiones (1:N)
- Una sesión → muchas ponencias (1:N)
- Una ponencia → pertenece a una sesión (N:1)
- Una ponencia ↔ varios ponentes (N:M) → ponencias_ponentes
- Un asistente ↔ varias conferencias (N:M) con fecha → inscripciones

---

## 4. Nota de normalización

El enunciado dice: “Una ponencia pertenece a una única sesión y conferencia”.

Diseño recomendado para evitar redundancia:

- sesiones incluye `id_conferencia` (FK)
- ponencias incluye `id_sesion` (FK)

Así, la conferencia de una ponencia se deduce a través de la sesión y se evita duplicar `id_conferencia` en ponencias (mejora hacia 3FN).
