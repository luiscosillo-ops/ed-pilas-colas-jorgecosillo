# Estructura de Datos: Cola (Queue)

Estructura FIFO (First In, First Out).

### 1. Operación enqueue(dato)
// Para encolar o meter un elemento al final de la fila
ALGORITMO enqueue(dato)
    SI cola_esta_llena() ENTONCES
        ESCRIBIR "Error: La cola está llena"
        RETORNAR
    FIN SI
    
    // Si es el primer elemento que entra, movemos el frente también
    SI estaVacia() ENTONCES
        frente <- 0
    FIN SI
    
    atras <- atras + 1
    cola[atras] <- dato
FIN ALGORITMO

### 2. Operación dequeue()
// Para atender o sacar al primero que llegó de la fila
ALGORITMO dequeue()
    SI estaVacia() ENTONCES
        ESCRIBIR "Error: La cola está vacía"
        RETORNAR NULL
    FIN SI
    
    valor <- cola[frente]
    
    // Si era el último elemento, reiniciamos los índices
    SI frente == atras ENTONCES
        frente <- -1
        atras <- -1
    SINO
        frente <- frente + 1
    FIN SI
    
    RETORNAR valor
FIN ALGORITMO

### 3. Operación peek()
// Miramos quién es el próximo en ser atendido sin sacarlo de la fila
ALGORITMO peek()
    SI estaVacia() ENTONCES
        ESCRIBIR "La cola está vacía"
        RETORNAR NULL
    FIN SI
    RETORNAR cola[frente]
FIN ALGORITMO

### 4. Operación estaVacia()
// Validación para verificar el estado de la cola
ALGORITMO estaVacia()
    SI frente == -1 ENTONCES
        RETORNAR VERDADERO
    SINO
        RETORNAR FALSO
    FIN SI
    
    // Nota personal: También se cumple si frente > atras en ciertas implementaciones
FIN ALGORITMO