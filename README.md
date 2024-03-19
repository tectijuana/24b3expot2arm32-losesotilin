# 3. Uso de registros y convenciones de llamadas

Tipos de registros:
- Registros de propósito general (R0-R7, R8-R10)
- Registros especializados (R11-R15): puntero de pila, puntero de enlace, puntero de instrucción, contador de programa

Convención de llamadas AAPCS (ARM Architecture Procedure Call Standard):
- R0-R3 se utilizan para pasar los primeros 4 argumentos a una función
- R0-R1 se utilizan para devolver valores de retorno de funciones
- R4-R11 son registros "cálidos" que deben preservarse a través de las llamadas a funciones
- R12 es el registro temporal volátil
- R13 (SP) es el puntero de pila
- R14 (LR) es el registro de enlace para almacenar la dirección de retorno
- R15 (PC) es el contador de programa

Registros de propósito general (R0-R7, R8-R10, R11-R15):
Estos registros se utilizan para diversos fines, como almacenar datos, direcciones y resultados intermedios en operaciones aritméticas y lógicas.
R7 se suele utilizar como manejador del sistema.
R11 se utiliza a menudo como puntero de trama para acceder a variables locales.
R12 es el registro scratch de llamada intra-procedimiento.
R13 se utiliza como puntero de pila para almacenar direcciones de retorno y variables locales.
R14 es el registro de enlace, que almacena la dirección de retorno después de una llamada a función.
R15 es el contador de programa, que contiene la dirección de la siguiente instrucción a ejecutar.

Registros especiales (CPSR/APSR):
Estos registros contienen información sobre el estado actual del procesador, incluyendo banderas de condición (N, Z, C, V) y otros bits de control (Q, GE, E, A, I, F, T, M).

Registros de dirección superior e inferior (R0-R15):
Se puede acceder a estos registros utilizando sus direcciones superior e inferior, lo que permite transferencias de datos y operaciones de memoria eficientes.

