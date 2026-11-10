# Ejercicio 5 — EPS SaludYa

Programación 1 · Universidad Libre · Docente: Andrés Castaño

## Cómo ejecutarlo

```bash
javac -d out src/*.java
java -cp out Main
```

## Qué hace

Asigna turnos consecutivos (T-001, T-002, ...) a los pacientes que los piden en las ventanillas o en el kiosco digital.

## Qué se resolvió

- **Antes:** cada ventanilla y cada llamada al kiosco creaba su propio `GeneradorTurnos` con `new`, y cada uno llevaba su propio consecutivo. Por eso varios pacientes recibían el mismo turno (T-001 repetido).
- **Ahora:** `GeneradorTurnos` es un **Singleton** (constructor privado y `getInstance()`). Todas las ventanillas y el kiosco comparten el mismo generador, los cinco pacientes reciben de T-001 a T-005 sin repetirse, y ninguna otra clase puede crear un generador nuevo con `new`
