# 3. Uso de registros y convenciones de llamadas

Esta imagen proporciona información detallada sobre los diferentes tipos de registros en la arquitectura ARM de 32 bits (ARM32) y cómo se utilizan para pasar argumentos y almacenar valores de retorno. Aquí hay un resumen de los puntos clave:

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

La imagen también cubre otros aspectos como instrucciones ARM, modos de ejecución condicional, ramificación y modos de cambio a Thumb (código compacto de 16 bits).

En resumen, proporciona una visión general detallada de los registros ARM32, su uso en la convención de llamadas AAPCS y conceptos relacionados con la arquitectura y las instrucciones ARM.
