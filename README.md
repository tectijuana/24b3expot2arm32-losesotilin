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
- R7 se suele utilizar como manejador del sistema.
- R11 se utiliza a menudo como puntero de trama para acceder a variables locales.
- R12 es el registro scratch de llamada intra-procedimiento.
- R13 se utiliza como puntero de pila para almacenar direcciones de retorno y variables locales.
- R14 es el registro de enlace, que almacena la dirección de retorno después de una llamada a función.
- R15 es el contador de programa, que contiene la dirección de la siguiente instrucción a ejecutar.

- Registros especiales (CPSR/APSR):
Estos registros contienen información sobre el estado actual del procesador, incluyendo banderas de condición (N, Z, C, V) y otros bits de control (Q, GE, E, A, I, F, T, M).

- Registros de dirección superior e inferior (R0-R15):
Se puede acceder a estos registros utilizando sus direcciones superior e inferior, lo que permite transferencias de datos y operaciones de memoria eficientes.

## EJEMPLOS

- R0-R3: Registros de propósito general comúnmente utilizados para operaciones aritméticas y lógicas.
Ejemplo: ADD R0, R1, R2 (R0 = R1 + R2)

- R4-R11: Registros de propósito general, a menudo utilizados para almacenar variables locales y direcciones de memoria.
Ejemplo: LDR R5, [R6] (Cargar el valor de la memoria apuntada por R6 en R5)

- R12: Registro de propósito general, comúnmente utilizado como registro temporal.
Ejemplo: MOV R12, R0 (Mover el valor de R0 a R12 para su uso posterior)

- R13 (SP): Registro del puntero de pila, utilizado para operaciones de pila.
Ejemplo: PUSH {R0-R3} (Empujar los valores de R0-R3 en la pila)
         SUB SP, SP, #16 (Ajustar el puntero de pila para reservar espacio en la pila)

- R14 (LR): Registro de enlace, utilizado para almacenar direcciones de retorno.
Ejemplo: BL función (Llamar a una función, la dirección de retorno se almacena en LR)

- R15 (PC): Contador de programa, apunta a la siguiente instrucción a ejecutar.
Ejemplo: LDR PC, [R0] (Cargar una nueva dirección desde R0 en el PC, cambiando el flujo de ejecución)

- CPSR: Registro de estado del programa actual, contiene banderas de condición y bits de control.
Ejemplo: MRS R0, CPSR (Mover el valor del CPSR a R0 para su inspección)

Espero que estos ejemplos más específicos y prácticos sean útiles para comprender mejor el uso de los registros en ARM.

![Captura de pantalla 2024-03-20 143556](https://github.com/tectijuana/24b3expot2arm32-losesotilin/assets/158230339/d093f91b-34e8-495c-8230-c9c333ab6bf6)
![Captura de pantalla 2024-03-20 143619](https://github.com/tectijuana/24b3expot2arm32-losesotilin/assets/158230339/5462c0f8-c0e9-4f1f-8436-43574f137806)
![Captura de pantalla 2024-03-20 143628](https://github.com/tectijuana/24b3expot2arm32-losesotilin/assets/158230339/23f88909-83b7-442e-ae1e-61a7991239de)
![Captura de pantalla 2024-03-20 143639](https://github.com/tectijuana/24b3expot2arm32-losesotilin/assets/158230339/da317c3e-7724-448d-977f-97a7f93c7448)
![Captura de pantalla 2024-03-20 143701](https://github.com/tectijuana/24b3expot2arm32-losesotilin/assets/158230339/14ba7d42-26a3-4182-bd48-f3f12fcf38fc)
![Captura de pantalla 2024-03-20 143714](https://github.com/tectijuana/24b3expot2arm32-losesotilin/assets/158230339/348d7e06-874d-4d8c-9a2b-6cf632d48010)
![Captura de pantalla 2024-03-20 143722](https://github.com/tectijuana/24b3expot2arm32-losesotilin/assets/158230339/374e3159-72b2-4b8f-b21a-2b8fa2dd2f04)
![Captura de pantalla 2024-03-20 143731](https://github.com/tectijuana/24b3expot2arm32-losesotilin/assets/158230339/7efdd6b0-84fc-406e-a18b-717dee17911f)
![Captura de pantalla 2024-03-20 143746](https://github.com/tectijuana/24b3expot2arm32-losesotilin/assets/158230339/a30e508e-edc1-497d-80ed-33c218b9be7c)
![Captura de pantalla 2024-03-20 143754](https://github.com/tectijuana/24b3expot2arm32-losesotilin/assets/158230339/0361ba88-beb9-4908-8ac3-5ba789fdb038)
![Captura de pantalla 2024-03-20 143802](https://github.com/tectijuana/24b3expot2arm32-losesotilin/assets/158230339/f98b295c-90eb-46f2-9b0f-534a7aacda3e)
![Captura de pantalla 2024-03-20 143810](https://github.com/tectijuana/24b3expot2arm32-losesotilin/assets/158230339/95419324-ea1b-440e-a523-76dfe06b0c9e)
