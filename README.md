# Paradigma-Logico

Repositorio correspondiente a la materia **Paradigmas de Programación (UTN)**.
En este proyecto se estudia y ejemplifica el **Paradigma Lógico** utilizando el lenguaje **Prolog**.

---

## Introducción al Paradigma Lógico

El **Paradigma Lógico** pertenece a la familia de los **paradigmas declarativos**, donde se especifica **qué relaciones existen entre los datos** y **qué se desea demostrar**, sin indicar cómo realizar la resolución paso a paso.
A diferencia del paradigma imperativo o funcional, el lógico se basa en la **deducción automática** de conclusiones a partir de un conjunto de hechos y reglas declaradas en una **base de conocimiento**.

---

## Características Fundamentales

* **Descriptivo:** los programas no indican cómo resolver un problema, sino que describen las relaciones lógicas entre las entidades del mismo.
* **Declarativo:** se expresa **qué se quiere obtener**, no **cómo lograrlo**.
* **Basado en lógica de primer orden:** utiliza **predicados** y **reglas lógicas** (cláusulas de Horn) para inferir conclusiones.
* **Sin algoritmo explícito:** el control de ejecución está a cargo del **motor de inferencias**, que aplica deducción, recursión y backtracking.
* **Transparencia referencial:** las variables se comportan como variables matemáticas, sin celdas de memoria ni efectos colaterales.

---

## Estructura de un Programa Lógico

Un programa lógico se compone de tres partes principales:

1. **Base de Conocimiento (BC):**
   Conjunto de hechos y reglas que representan el conocimiento del dominio.

   * **Hechos:** enunciados siempre verdaderos que describen relaciones básicas.

     ```prolog
     gusta(maria, juan).
     hombre(juan).
     mujer(maria).
     ```

   * **Reglas:** permiten deducir nuevos hechos a partir de los existentes.

     ```prolog
     amigo(X, Y) :- gusta(X, Y), mujer(X), hombre(Y).
     ```

2. **Consultas:**
   Se formulan para **demostrar un objetivo** a partir de la base de conocimiento.

   * **Validación:** responde *Sí* o *No*.

     ```prolog
     ?- mujer(maria).  % Respuesta: Yes
     ```

   * **Búsqueda:** devuelve los valores que satisfacen la consulta.

     ```prolog
     ?- gusta(maria, X).  % Respuesta: X = juan
     ```

3. **Motor de Inferencias:**
   Controla la ejecución del programa mediante **unificación**, **resolución** y **backtracking**, buscando las soluciones que satisfacen la consulta.

---

## Conceptos Clave

* **Unificación:** proceso por el cual las variables de una consulta se asocian con valores de los hechos o reglas.
* **Backtracking:** mecanismo de búsqueda recursiva que explora distintas ramas del árbol de inferencias.
* **Resolución:** proceso de demostración, emparejando objetivos con la cabeza de reglas y verificando subcondiciones.
* **Reversibilidad:** permite consultar a partir de datos conocidos o inferir qué datos producirían un resultado determinado.

---

## Tipos de Consultas

* **Sin Variables:** validación directa de un hecho.
* **Con Variables:** búsqueda de valores que satisfacen la consulta.
* **Con Variable Anónima:** consulta de existencia sin identificar el valor exacto.

```prolog
?- gusta(maria, _).  % Respuesta: Yes
```

---

## Hipótesis del Mundo Cerrado

Todo lo que **no está especificado en la Base de Conocimiento se considera falso**.
Esto permite que el sistema asuma con seguridad que un hecho ausente es no verdadero.

---

## Listas en Prolog

Las listas son estructuras **homogéneas y recursivas** utilizadas para almacenar colecciones de elementos.

* Se representan como secuencias de elementos delimitadas por corchetes.
* La lista vacía se denota con `[]`.
* La cabeza y cola de una lista se representan mediante `[X | Xs]`.
* Pueden recorrerse recursivamente y contener variables, constantes o estructuras anidadas.

```prolog
% Longitud de una lista
long([], 0).
long([_ | Xs], L) :- long(Xs, L1), L is L1 + 1.

% Suma de elementos de una lista
sum([], 0).
sum([X | Xs], S) :- sum(Xs, S1), S is X + S1.
```

---

## Pasos de la Programación Lógica

1. **Modelar el problema** mediante una base de conocimiento formada por hechos.
2. **Definir reglas** que representen las relaciones lógicas entre los hechos.
3. **Formular consultas** para deducir o demostrar respuestas a partir de la base de conocimiento.

---

## Aplicaciones del Paradigma Lógico

* **Inteligencia Artificial**
* **Sistemas Expertos**
* **Robótica**
* **Procesamiento de Lenguaje Natural (NLP)**
* **Compiladores y análisis semántico**
* **Bases de datos deductivas**
* **Acceso a información en la web mediante lógica**

---

## Lenguaje PROLOG

**Prolog (Programmation en Logique)** es el lenguaje más representativo del paradigma lógico.
Es un **lenguaje interpretado** que cuenta con compilador, intérprete interactivo, shell de ejecución y biblioteca estándar.
Prolog combina **lógica y control** para la resolución de consultas sobre bases de conocimiento.

---

## Conceptos Finales

* **Sin instanciar:** una variable no unificada aún no tiene valor asignado.
* **Motor de inferencias:** aplica recursión, unificación y backtracking para demostrar objetivos.
* **Hipótesis del mundo cerrado:** todo lo no declarado se asume falso.
* **Reversibilidad:** permite razonamiento bidireccional entre causas y consecuencias.

---

## Ejecución en Prolog

Para ejecutar programas en **Prolog** de manera clara y efectiva, se pueden seguir estos pasos:

1. **Guardar el archivo:**
   Guardá tu programa lógico con extensión `.pl`.
   Ejemplo: `base_conocimiento.pl`

2. **Abrir el intérprete de Prolog:**
   Podés usar **SWI-Prolog** o **GNU Prolog**. Desde la terminal se ejecuta:

   ```bash
   swipl
   ```

3. **Cargar el archivo en el intérprete:**

   ```prolog
   ?- [base_conocimiento].
   ```

4. **Realizar consultas:**

   ```prolog
   ?- gusta(maria, X).
   ?- amigo(maria, juan).
   ```

5. **Ejecución directa desde Bash (opcional):**

   ```bash
   swipl -s base_conocimiento.pl -g "gusta(maria, X), writeln(X), halt."
   swipl -s base_conocimiento.pl -g "sum([2,7,3], S), writeln(S), halt."
   ```

   * `-s` indica el archivo de Prolog a cargar.
   * `-g` indica la consulta a ejecutar al iniciar.
   * `writeln(X)` imprime la respuesta en consola.
   * `halt.` cierra Prolog automáticamente al finalizar.
