# Ejercicio 2 — Debugging SQL con Ollama (mistral:7b)

## Código con errores (dado en el enunciado)

```sql
CREATE TABLE clientes (
    id_cliente INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100),
    email VARCHAR(50) UNIQUE,
    fecha_registro DATE DEFAULT NOW(),
    edad INT CHECK edad > 18,
    saldo DECIMAL(10,2) DEFAULT 0,
    PRIMARY KEY (id_cliente)
);
```

## Paso 1: detectar problemas visualmente (sin ejecutar)

Cosas “sospechosas”:

Hay PRIMARY KEY duplicada (una en la columna y otra al final).

DEFAULT NOW() en un campo DATE puede dar problemas (NOW() devuelve fecha + hora).

CHECK está mal escrito: falta paréntesis en la condición.

nombre no tiene NOT NULL (no es error, pero suele ser recomendable).

## Paso 2: consulta a Ollama (sin pedir solución directa)

```markdown
Este código SQL tiene varios errores. Identifícalos uno por uno y explica cómo corregirlos.

No me des la solución directa. Dame pistas sobre:
1. Sintaxis incorrecta
2. Redundancias
3. Uso incorrecto de funciones

[pego el código aquí]
```

## Paso 3: mi versión corregida (validada en MySQL)

```sql
CREATE TABLE clientes (
  id_cliente INT AUTO_INCREMENT NOT NULL,
  nombre VARCHAR(100) NOT NULL,
  email VARCHAR(50) NOT NULL UNIQUE,
  fecha_registro DATE NOT NULL DEFAULT (CURRENT_DATE),
  edad INT NOT NULL CHECK (edad > 18),
  saldo DECIMAL(10,2) NOT NULL DEFAULT 0.00,
  PRIMARY KEY (id_cliente)
);
```
