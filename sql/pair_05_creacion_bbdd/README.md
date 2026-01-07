# Pair 05 — Creación de BD (Tienda de zapatillas) + Debugging con Ollama

En este pair creamos una base de datos desde cero para una tienda de zapatillas, con 4 tablas:

- empleados
- clientes
- zapatillas
- facturas

La tabla `facturas` se relaciona con las otras tres mediante claves foráneas.

Además, realizamos un ejercicio de debugging de SQL con ayuda de Ollama (mistral:7b).

---

## Estructura de esta carpeta

```text
sql/pair_05_creacion_bbdd/
├── README.md
├── tienda_zapatillas.sql
└── ollama_debugging.md
```

### 1) Creación de la base de datos y tablas (tienda_zapatillas)

#### Objetivo

Crear el schema tienda_zapatillas y las tablas con sus columnas y restricciones según el enunciado.

#### Cómo ejecutar

- Abrir MySQL Workbench y conectarse a tu servidor MySQL.

- Abrir el archivo tienda_zapatillas.sql.

- Ejecutar el script completo.

#### Tablas y relaciones

- empleados (PK: id_empleado)

- clientes (PK: id_cliente)

- zapatillas (PK: id_zapatilla)

- facturas (PK: id_factura)

  - FK id_empleado → empleados.id_empleado

  - FK id_cliente → clientes.id_cliente

  - FK id_zapatilla → zapatillas.id_zapatilla

### 2) Debugging con Ollama

Ejercicio para detectar errores comunes en SQL con ayuda de Ollama y aprender a corregirlos paso a paso.

➡️ Ver pasos, prompts y versión final corregida en: ollama_debugging.md

#### Herramientas

MySQL Workbench

MySQL 8.x

Ollama + mistral:7b
