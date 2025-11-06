# Operadores en Prolog

En Prolog, los **operadores** son símbolos o palabras reservadas que permiten realizar **comparaciones, cálculos, unificaciones y control de flujo** dentro de un programa lógico.  
Existen diferentes tipos de operadores según su funcionalidad: aritméticos, de comparación, lógicos, de unificación, entre otros.  

---

## Tipos de Operadores en Prolog

### 1. Operadores Aritméticos

Se utilizan para realizar **operaciones matemáticas** sobre números.  
Incluyen operaciones básicas como suma, resta, multiplicación, división, potencia, módulo y raíces.  
Estos operadores requieren que los operandos sean números y permiten **evaluaciones deterministas** dentro de las reglas.

---

### 2. Operadores de Comparación

Se emplean para **comparar valores** y generar condiciones en reglas y consultas.  
Existen dos categorías principales:  

- **Comparaciones aritméticas:** verifican relaciones numéricas como mayor que, menor que, igualdad o desigualdad.  
- **Comparaciones exactas:** permiten comparar términos sin evaluarlos, verificando que sean idénticos o distintos.  

---

### 3. Operadores Lógicos

Facilitan la combinación y negación de condiciones dentro de reglas o consultas.  
Los más importantes incluyen:

- **Conjunción (``,`):** se cumple si ambas condiciones son verdaderas.  
- **Disyunción (`;`):** se cumple si al menos una de las condiciones es verdadera.  
- **Negación (`\+`):** se cumple si la condición es falsa, implementando la lógica de “no”.  

---

### 4. Operadores de Unificación

El operador principal de Prolog es **la unificación (`=`)**, que permite **asignar valores a variables** y verificar si dos términos pueden coincidir.  
También existen operadores complementarios:

- **`==` y `\==`**: verifican igualdad o desigualdad exacta sin unificar variables.  
- **`=:=` y `=\=`**: comparan valores aritméticos evaluados.  
- **`<`, `>`, `=<`, `>=`**: comparaciones aritméticas que verifican relaciones entre números.

---

### 5. Operadores de Entrada/Salida y Control

Prolog incluye operadores que facilitan **la interacción con el usuario** y el **flujo de ejecución** de programas:

- **`is`**: evalúa expresiones aritméticas y asigna resultados a variables.  
- **`fail`**: fuerza el retroceso (backtracking) en la búsqueda de soluciones.  
- **`cut` (`!`)**: controla el backtracking, evitando la exploración de alternativas no deseadas.  

---

### 6. Operadores Especiales

Algunos operadores se utilizan para manipular **estructuras de datos complejas** como listas o estructuras:

- **Lista:** el operador de cabeza y cola `[X|Xs]` permite descomponer listas.  
- **Concatenación y construcción de estructuras** mediante `.` o paréntesis para términos compuestos.  

---

## Conceptos Clave sobre Operadores en Prolog

- **Determinismo:** muchos operadores producen resultados únicos, mientras que otros pueden generar múltiples soluciones mediante backtracking.  
- **Evaluación perezosa:** Prolog evalúa los operadores según sea necesario, permitiendo eficiencia y control de flujo.  
- **Unificación como núcleo:** la mayoría de las operaciones dependen de la capacidad de unificar variables y términos para derivar soluciones.  
- **Negación basada en fallos:** la negación no se evalúa como “falsa” directamente, sino mediante la imposibilidad de unificar o demostrar un objetivo.