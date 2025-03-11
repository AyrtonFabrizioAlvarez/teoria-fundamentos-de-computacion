# Practica 1 Fundamentos de Teoria de la Computacion

### Ejercicio 1. Responder breve y claramente los siguientes incisos:

**1. ¿En qué se diferencia un problema de búsqueda de un problema de decisión?**  
Un <u>*problema de decisión*</u> es aquel cuya respuesta es "sí" o "no". Es decir, se trata de determinar si una entrada cumple con una condición determinada.  
Un <u>*problema de búsqueda*</u>, en cambio, requiere encontrar una solución específica cuando esta existe. No basta con responder "sí" o "no", sino que se debe proporcionar un ejemplo concreto de la solución.  
<u>**Ejemplo:**</u>   
*Problema de decisión: ¿Existe una asignación de valores de verdad que hace verdadera una fórmula booleana? SAT (satisfactibilidad booleana)*  
*Problema de búsqueda: Encontrar una asignación de valores de verdad que haga verdadera la fórmula.*
  
**2. ¿Por qué en el caso de los problemas de decisión, podemos referirnos indistintamente a problemas y lenguajes?**  
Un problema de decisión es un conjunto de preguntas con respuesta "sí" o "no".  
Un lenguaje es un conjunto de cadenas sobre un alfabeto.  
¿Por qué podemos referirnos a problemas de decisión como lenguajes?  
Porque podemos representar cualquier problema de decisión como un conjunto de cadenas que representan los casos donde la respuesta es "sí".  
<u>**Ejemplo:**</u>  
*Problema de decisión:*  ¿Es satisfactible la fórmula φ?  
*Lenguaje asociado:*  Conjunto de todas las fórmulas satisfactibles.  
Matemáticamente, si definimos 𝐿 como el conjunto de todas las fórmulas que son satisfactibles, entonces podemos escribirlo como:  
*𝐿 = {𝜙∣𝜙 es una formula booleana satisfactible}*
Así, resolver el problema de decisión SAT es equivalente a preguntar si una fórmula 𝜙 pertenece al lenguaje 𝐿.  
<u>En general, cualquier problema de decisión puede expresarse como el lenguaje de las instancias que responden "sí".</u>
  
**3. El problema de satisfactibilidad de las fórmulas booleanas, en su forma de decisión, es: “Dada una  fórmula  φ,  ¿existe  una  asignación  A  de valores de  verdad  que  la  hace  verdadera?”**  
**Enunciar el problema de búsqueda asociado.**  
El problema de búsqueda SAT es:  
**Dada una fórmula booleana φ, encontrar una asignación A de valores de verdad a sus variables que la haga verdadera, si tal asignación existe.**  
Si la fórmula no es satisfactible, el problema de búsqueda no tiene solución.
  
**4. Otra visión de MT es la que genera un lenguaje (visión generadora). En el caso del problema del  inciso  anterior,  ¿qué  lenguaje  generaría  la  MT  de  visión  generadora  que  resuelve  el problema?**  
Una Máquina de Turing (MT) de visión generadora para SAT generaría el conjunto de todas las asignaciones de valores de verdad que satisfacen una fórmula dada.  
Es decir, generaría el siguiente lenguaje:  
*𝐿={(𝜙,𝐴)∣𝐴 es una asignacion de valores de verdad que satisface 𝜙}*  
**(Cada palabra en este lenguaje representa una pareja (φ, A), donde φ es una fórmula booleana y A es una asignación de verdad que la satisface.)**  
<u>**Ejemplo: Supongamos la formula:**</u>  
- 𝜙 = (x ∨ y) (OR)  

Las asignaciones que satisfacen la fórmula son: 
- 𝐴1 = (x=0,y=1)  
- A2 = (x=1,y=0)  
- A3 = (x=1,y=1)  

El lenguaje generado por la MT sería:  
- 𝐿 = {(𝜙,𝐴1),(𝜙,𝐴2),(𝜙,𝐴3)}  

Es decir, la MT genera todas las asignaciones que hacen verdadera la fórmula.  
Si en cambio la fórmula fuera insatisfactible, la MT no generaría nada.  
  
**5. ¿Qué postula la Tesis de Church-Turing?**   
La Tesis de Church-Turing dice que **todo problema resoluble mediante un algoritmo puede resolverse con una Máquina de Turing.**  
Se basa en el hecho de que **todos los modelos formales de computación conocidos son equivalentes a las Máquinas de Turing.**  
Define los límites de la computación, estableciendo que ciertos problemas simplemente no pueden resolverse algorítmicamente.  

<u>**Ejemplo de problemas computables:**</u>  
- Sumar dos números.
- Encontrar el camino más corto en un grafo.
- Determinar si una palabra pertenece a un lenguaje regular.  

<u>**Ejemplo de problemas NO computables:**</u>  
- Determinar si cualquier programa arbitrario se detendrá o se ejecutará para siempre (Problema de la Parada).
- Generar la lista completa de teoremas verdaderos en matemáticas (Problema de Entscheidungsproblem de Hilbert).
  
**6. ¿Cuándo dos MT son equivalentes? ¿Y cuándo dos modelos de MT son equivalentes?**  
<u>*Dos Máquinas de Turing son equivalentes si*</u> reconocen el mismo lenguaje o computan la misma función. Es decir, para toda entrada, producen la misma salida (ya sea aceptación/rechazo o un resultado computacional).  
<u>*Dos modelos de Máquinas de Turing son equivalentes si*</u> pueden simularse mutuamente sin pérdida de capacidad computacional.  
<u>**Ejemplo:**</u>  
Una Máquina de Turing con múltiples cintas es equivalente a una Máquina de Turing de una sola cinta, porque podemos transformar un programa de una en el otro sin cambiar su capacidad de cómputo. 
  