Proyecto divisas
## loaiza 1 — Modelo POO (herencia y polimorfismo)

**Archivos**
- `modelo/`: Persona, Cliente, ClienteGeneral, ClientePreferencial, ClienteEmpresarial, Empleado, Cajero, Administrador, Transaccion, CambioDivisa, Reversion
- `negocio/`: Tasa, Caja

**Debe saber explicar en la sustentación**
- Qué es una clase abstracta y por qué Persona, Cliente, Empleado y Transaccion lo son.
- Cómo `calcularComision()` da 1,5 %, 1,0 % y 0,8 % sin un solo `if` por tipo (cada subclase sobrescribe `getPorcentajeComision()`).
- El `super(id, nombre)` del constructor de ClienteEmpresarial y el `super.mostrarDetalle()` de CambioDivisa.
- Por qué `puedeActualizarTasas()` es `false` en Empleado y solo Administrador lo sobrescribe.
- Cómo Caja usa arreglos de 5 posiciones (uno por divisa), y cómo `restituir()` deshace lo que hizo `actualizarSaldo()`.

**Casos de prueba que documenta:** 11, 12 y 14.
**Pseudocódigo:** calcularComision, esEfectiva, restituir.

---

## tomas 2 — Estructuras de datos y consultas

**Archivos**
- `estructuras/`: Nodo, Lista, Cola, Pila
- `negocio/`: Consultas (C1 a C12)

**Debe saber explicar en la sustentación**
- Por qué la Cola es FIFO (atención en orden de llegada) y la Pila es LIFO (deshacer la última operación).
- Cómo `eliminar()` de la lista maneja la primera, una intermedia y la última posición.
- La diferencia entre `cima()` (consultar) y `desapilar()` (sacar).
- Que `desencolar()` y `desapilar()` retornan `null` si están vacías, para no romper el programa.
- Cómo `ordenarPorMonto()` ordena por inserción sin usar colecciones de Java.
- Qué funciones intervienen en cada consulta C1 a C12.

**Casos de prueba que documenta:** 1, 5 y 10.
**Pseudocódigo:** encolar, desencolar, apilar, desapilar, eliminar, ordenarPorMonto.

---

## liscano 3 — Lógica del negocio, archivos y menú

**Archivos**
- `negocio/`: CasaDeCambio
- `persistencia/`: GestorArchivos
- `app/`: Main, Pruebas
- `datos/` y `datos_prueba/`

**Debe saber explicar en la sustentación**
- La regla de 2 preferenciales por cada general (`atenderSiguiente()` con `contadorPreferenciales`).
- El flujo de `procesarCambio()`: validar, convertir, comisión, saldo; luego COMPLETADA y a la pila, o RECHAZADA.
- `convertir()`: par directo, luego par inverso, luego puente por COP (EUR→MXN = EUR→COP→MXN).
- `revertirUltima()`: desapila, marca REVERSADA, restituye caja e inserta una Reversion de auditoría.
- Cómo se lee cada archivo línea por línea, y que una línea corrupta se omite e informa sin detener la carga.
- Cómo se reconstruye cada transacción en su clase según el primer campo (CAMBIO o REVERSION).
- Permisos: solo el administrador actualiza tasas y cierra el turno.

**Casos de prueba que documenta:** 2, 3, 4, 6, 7, 8, 9, 13 y 15.
**Pseudocódigo:** procesarCambio, revertirUltima, atenderSiguiente, convertir, cargarTransacciones.

---

