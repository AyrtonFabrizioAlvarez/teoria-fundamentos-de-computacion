# Practica 4 Fundamentos de Teoria de la Computacion  

## Ejercicio 1. Considerando la reducción de HP a LU descripta en clase, responder: 
- a. Explicar por qué la función identidad, es decir la función que a toda cadena le asigna la misma cadena, no es una reducción de HP a LU.
  - La función de identidad no es una reduccion de HP a LU ya que tendriamos problemas con la correctitud, porque teniendo una maquina HP que recibe una entrada ( < M1 >, w ) podriamos tener 2 casos donde ( < M1 >, w ) ∈ HP.
  - caso 1: ( < M1 >, w ) ∈ HP -> M1 acepta w y M2 acepta w ya que  ( < M2 >, w ) ∈ LU **aca no tenemos ningún problema (HP termina en QA y LU termina en QA)**
  - caso 2: ( < M1 >, w ) ∈ HP -> M1 rechaza w y M2 rechaza w ya que ( < M2 >, w ) ∉ LU
- b. Explicar por qué las MT M2 generadas en los pares de salida (< M2 >, w), o bien paran aceptando, o bien loopean. 
- c. Explicar por qué la función utilizada para reducir HP a LU también sirve para reducir HPC a LUC. 
- d. Explicar por qué la función utilizada para reducir HP a LU no sirve para reducir LU a HP. 
- e. Explicar por qué la siguiente MT Mf no computa una reducción de HP a LU: dada una cadena válida (<M>, w), Mf ejecuta M sobre w, si M acepta entonces genera la salida (<M>, w), y si M rechaza entonces genera la cadena 1.  
 
## Ejercicio 2. Sabiendo que LU ∈ RE y LUC ∈ CO-RE: 
- a. Probamos en clase que existe  una reducción de LU  a LƩ*.  En base a esto,  ¿qué se puede afirmar con respecto a la ubicación de LƩ* en la jerarquía de la computabilidad? 
- b. Se prueba que existe una reducción de LUC a L. En base a esto, ¿qué se puede afirmar con respecto a la ubicación de L en la jerarquía de la computabilidad? 
 
## Ejercicio  3.  Sea el lenguaje DHP  = {wi  | Mi  para  a partir de  wi} (considerar  el orden  canónico). Encontrar  una  reducción  de  DHP  a  HP.  Comentario:  hay  que  definir  la  función  de  reducción  y probar su total computabilidad y correctitud.  
 
## Ejercicio 4. Sean TAUT y NOSAT los lenguajes de las fórmulas booleanas sin cuantificadores tautológicas  (satisfactibles  por  todas  las  asignaciones  de  valores  de  verdad)  e  insatisfactibles (insatisfactibles por todas las asignaciones de valores de verdad). Encontrar una reducción de TAUT  a  NOSAT.  Comentario:  hay  que  definir  la  función  de  reducción  y  probar  su  total computabilidad y correctitud.  
 
## Ejercicio 5. Se prueba que existe una reducción de LUC a LƩ* (y así, como LUC ∉ RE, entonces se cumple que LƩ* ∉ RE). La reducción es la siguiente. Para toda w: f((< M1 >, w)) = < M2 >, tal que M2, a partir de su entrada v, ejecuta |v| pasos de M1 a partir de w, y acepta sii M1 no acepta. Probar que la función definida es efectivamente una reducción de LUC a LƩ*. Comentario: hay que probar su total computabilidad y correctitud.  