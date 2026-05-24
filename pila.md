
# Estructura de Datos: Pila (Stack)

En este archivo presento el pseudocódigo para el comportamiento de una Pila, utilizando la lógica LIFO (Last In, First Out).

### 1. Operación push(dato)
// Insertamos un elemento en la cima de la pila
ALGORITMO push(dato)
    // Primero validamos si hay espacio en memoria (en caso de arreglos fijos)
    SI pila_esta_llena() ENTONCES
        ESCRIBIR "Error: Desbordamiento de pila (Stack Overflow)"
        RETORNAR
    FIN SI
    
    // Incrementamos el tope y guardamos el dato
    tope <- tope + 1
    pila[tope] <- dato
FIN ALGORITMO

### 2. Operación pop()
// Remueve y retorna el elemento que está en la cima
ALGORITMO pop()
    // Si no hay nada, no podemos sacar nada
    SI estaVacia() ENTONCES
        ESCRIBIR "Error: La pila está vacía (Stack Underflow)"
        RETORNAR NULL
    FIN SI
    
    // Guardamos el valor actual para devolverlo y bajamos el tope
    valor <- pila[tope]
    tope <- tope - 1
    RETORNAR valor
FIN ALGORITMO

### 3. Operación peek()
// Solo para echar un ojo al elemento de arriba sin alterarlo
ALGORITMO peek()
    SI estaVacia() ENTONCES
        ESCRIBIR "La pila está vacía"
        RETORNAR NULL
    FIN SI
    RETORNAR pila[tope]
FIN ALGORITMO

### 4. Operación estaVacia()
// Control básico para saber si tenemos elementos
ALGORITMO estaVacia()
    SI tope == -1 ENTONCES
        RETORNAR VERDADERO
    SINO
        RETORNAR FALSO
    FIN SI
FIN ALGORITMO