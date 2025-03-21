# Practica 2 Fundamentos de Teoria de la Computacion  
## Ejercicio 1. Responder breve y claramente los siguientes incisos:  
### 1. ¿En qué se diferencian los lenguajes recursivos, los lenguajes recursivamente numerables no recursivos y los lenguajes no recursivamente numerables?  
**Lenguajes recursivos (decidibles):**  
Son aquellos para los cuales existe una Máquina de Turing (MT) que, para cualquier cadena de entrada, siempre se detiene y decide (acepta o rechaza). 

**Lenguajes recursivamente numerables (RE) que no son recursivos (semi-decidibles):**  
Son lenguajes para los cuales existe una MT que acepta las cadenas del lenguaje, pero en caso de que la cadena no pertenezca al lenguaje, la MT puede entrar en un bucle infinito (no se garantiza la detención).

**Lenguajes no recursivamente numerables:**  
Son lenguajes para los cuales no existe ninguna MT que pueda, aun en forma semi-decidible, enumerar todas las cadenas del lenguaje. Es decir, ni siquiera se puede construir una máquina que, al menos, acepte las cadenas pertenecientes al lenguaje.

### 2. Probar que R ⊆ RE ⊆ 𝔏. Ayuda: usar las definiciones.  
**R ⊆ RE:**  
Si un lenguaje es recursivo, existe una MT que siempre se detiene decidiendo la pertenencia de cualquier cadena. Por lo tanto, tomando esa misma MT se tiene que, cuando la cadena pertenece al lenguaje, la máquina la acepta. Esto implica que todo lenguaje decidible es, a la vez, recursivamente numerable.

**RE ⊆ 𝔏:**  
Todo lenguaje recursivamente numerable (RE) es un subconjunto de Σ* (el conjunto de todas las cadenas sobre el alfabeto Σ). En otras palabras, son lenguajes (conjuntos de cadenas) y, por definición, todo lenguaje pertenece a la familia 𝔏 de lenguajes.

### 3. Dijimos en clase que el hecho de que si L es recursivo entonces LC también lo es, significa en  términos  de  problemas  que  si  un  problema  es  decidible  entonces  también  lo  es  el problema  contrario.  ¿Qué  significa  en  términos  de  problemas  que  la  intersección  de  dos lenguajes recursivos es también un lenguaje recursivo?  
Si tenemos una MT1 que resuelve un lenguaje L1, y una MT2 que resuelve un lenguaje L2 (L1 ^ L2 ∈ R), entonces existe una MT3 que resuelve un lenguaje L3 (L3 ∈ R) entonces vemos que L3 es la interseccion entre L1 ^ L2  
![ejercicio1.3](./imagenes/trabajo2-ejercicio1.3.jpeg)  
**En terminos de problemas, si un lenguaje L1 es recursivo y un lenguaje L2 es recursivo, la intersecciond de estos L3 es tambien recursivo, entonces si tengo 2 problemas decidibles, la interseccion de estos 2 problemas, es tambien decidible, (en la interseccion entendemos que el problema comun a ambos problemas que participan en la interseccion es tambien decidible)**  

### 4. Explicar por qué no es correcta la siguiente prueba de que si L ∈ RE, también LC ∈ RE: dada una  MT  M  que  acepta  L,  entonces  la  MT  M’,  igual  que  M  pero  con  los  estados  finales permutados, acepta LC.  
**Problema del loop:**  
La máquina original M, que acepta L, garantiza que cuando una cadena w está en L se detendrá aceptándola; sin embargo, cuando la cadena w no pertenece a L, M puede no detenerse (entrar en un bucle infinito). Simplemente intercambiar los estados de aceptación y no aceptación no soluciona el problema de la detención, ya que M′ no tiene control sobre las computaciones infinitas de M.  
![ejercicio1.4](./imagenes/trabajo2-ejercicio1.4.png)  

### 5. ¿Qué lenguajes de la clase CO-RE tienen MT que los aceptan? ¿También los deciden?  
### <u>CONSULTAR</u>  
**Definición de CO-RE:**  
Son aquellos lenguajes cuyo complemento es recursivamente numerable (L ∈ CO-RE ^ LC ∈ RE).

**Máquinas que los aceptan:**  
Si un lenguaje L ∈ CO-RE, el lenguaje LC ∈ RE, entonces los lenguajes de CO-RE que tienen MT que los aceptan son aquellos lenguajes L ∈ CO-RE cuyo complemento LC ∈ RE tienen una MT que los rechaza (por lo que la MT que decide el lenguaje de CO-RE lo acepta)  
LA MT QUE DECIDE L ∈ CO-RE NO SIEMPRE ACEPTARIA POR EL POTENCIAL LOOP DE LA MT QUE DECIDE LC ∈ RE

**Decisión:**  
Los lenguajes en CO-RE, en general, no son decidibles a menos que además pertenezcan a RE (en cuyo caso serían recursivos ya que RE ⋂ CO-RE ⊆ R). Por ello, en CO-RE podemos tener máquinas que aceptan (semi-decidibilidad) pero no necesariamente deciden el lenguaje.

### 6. Probar que el lenguaje Ʃ* de todas las cadenas y el lenguaje vacío ∅ son recursivos. Alcanza con plantear la idea general. Ayuda: encontrar MT que los decidan.  
### <u>CONSULTAR</u>  
**Si tenemos un lenguaje L (Σ de todas las cadenas) y su LC (el lenguaje vacío), si construimos una MT M que decida L, entonces seguro tenemos una MT M2 que decide LC**  

**Lenguaje Σ (todas las cadenas):**  
Se puede construir una MT que, para cualquier entrada, simplemente acepte sin realizar ningún cómputo complejo. Esta máquina siempre se detiene aceptando, lo que demuestra que Σ* es recursivo.

**Lenguaje vacío (∅):**  
De manera similar, se puede diseñar una MT que, para cualquier entrada, rechace de forma inmediata. Dado que la máquina se detiene en todos los casos, ∅ es recursivo.

La idea central es definir máquinas de Turing “triviales” que no necesitan realizar cálculos complejos y siempre se detienen con una respuesta.

### 7. Probar que todo  lenguaje finito  es recursivo.  Alcanza  con  plantear la idea general.  Ayuda: encontrar una MT que lo decida (pensar cómo definir sus transiciones para cada una de las cadenas del lenguaje).  
### <u>CONSULTAR</u>   
En este caso necesitamos construir una MT que ante cualquier cadena de un lenguaje L que es finito acepte, en este caso si la cadena w no se encuentra en el lenguaje L finito, la MT rechaza. Es por esto mismo que no entraria en loop nunca y decimos que el lenguaje L es recursivo (R).



## Ejercicio 2. Considerando la Propiedad 2 estudiada en clase:  
### <u>CONSULTAR</u>  
### 1. ¿Cómo implementaría la copia de la entrada w en la cinta 2 de la MT M?  
**Paso 1: Por cada posicion de la cinta 1 con un simbolo <> B:**  
- Copiar el simbolo encontrado en la cinta 1 a la cinta 2
- Mover ambos cabezales a la derecha

**Paso 2: UNa vez copiada toda la informacion, se pasa a estados adicionales que indican que MT deberia decidir w**

### 2. ¿Cómo implementaría el borrado del contenido de la cinta 2 de la MT M?  
**Paso 1: Posicionar el cabezal de la cinta 2 en el inicio.**  
**Paso 1: Por cada posicion en la cinta 2 con un simbolo <> B:**  
- Escribir el símbolo B en la cinta 2.
- Mover el cabezal de la cinta 2 a la derecha.  

**Paso 2: Una vez borrada toda la información, se puede reposicionar el cabezal en la posición inicial (usando estados adicionales) para continuar con la siguiente fase de la computación ya que .**  



## Ejercicio 3. Probar: 
### 1. La clase R es cerrada con respecto a la operación de unión. Ayuda: la prueba es similar a la desarrollada para la intersección.  
Si existe una MT M1 que decide un lenguaje L1, y existe una MT M2 que decide un lenguaje L2 (L1 ^ L2 ∈ R), entonces podemos construir una MT M3 que decide un lenguaje L3 (L3 = L1 ⋃ L2), es decir, **<u>M3 acepta si M1 ó M2 aceptan</u>**  
![ejercicio3.1](./imagenes/trabajo2-ejercicio3.1.png)  


### 2. La clase RE es cerrada con respecto a la operación de intersección. Ayuda: la prueba es similar a la desarrollada para la clase R.  
Si existe una MT M1 que acepta un lenguaje L1, y existe una MT M2 que acepta un lenguaje L2 (L1 ^ L2 ∈ RE), entonces podemos construir una MT M3 que acepta un lenguaje L3 (L3 = L1 ⋂ L2), es decir, **<u>M3 acepta si M1 y M2 aceptan</u>**
![ejercicio3.2](./imagenes/trabajo2-ejercicio3.2.png)



## Ejercicio  4.
### Sean  L1  y  L2  dos  lenguajes  recursivamente  numerables  de  números  naturales codificados en unario (por ejemplo, el número 5 se representa con 11111). Probar que también es recursivamente numerable el lenguaje L = {x | x es un número natural codificado en unario, y existen y, z, tales que y + z = x, con y ∈ L1, z ∈ L2}.  Ayuda: la prueba es similar a la vista en clase, de la clausura de la clase RE con respecto a la operación de concatenación.  
Tenemos una MT M1 que acepta un lenguaje L1 y tenemos una MT M2 que acepta un lenguaje L2 (L1 ^ L2 ∈ RE) y queremos probar que existe una MT M3 que acepta un lenguaje L3, donde L3 = L1 . L2, y por lo tanto L3 ∈ RE.  

La idea consta de ir subdividiendo la cadena w de tamaño n de la siguiente manera:
- MT M1 recibe una particion de tamaño 0 de w y MT M2 recibe una particion de tamaño N de w, si ambas aceptan MT M3 acepta
- sino, se vuelve a correr el paso 1, pero MT M1 recibe una particion de tamaño 1 y MT M2 recibe una particion de tamaño n-1, si ambas aceptan MT M3 acepta
- sino, se vuelve a correr el paso 1 sucesivamente con tamaños de particion (2, N-2), (3, N-3), (4, N-4) hasta el paso donde quede (N, 0)
 
Para construir esta MT M3 tenemos que considerar los posibles loops inherentes de los lenguajes RE, entonces lo hacemos "por pasos" simulando una ejecucion "en paralelo":
- primero hacemos 1 paso de ejecuciones de M1 y M2 con TODAS LAS POSIBLES PARTICIONES DE W
- luego hacemos 2 pasos de ejecuciones de M1 y M2 con TODAS LAS POSIBLES PARTICIONES DE W
- luego hacemos E pasos de ejecuciones de M1 y M2 con TODAS LAS POSIBLES PARTICIONES DE W
- asi seguimos hasta eventualmente aceptar



## Ejercicio 5. Dada una MT M1 con alfabeto Γ = {0, 1}: 
### 1. Construir una MT M2, utilizando la MT M1, que acepte, cualquiera sea su cadena de entrada, sii la MT M1 acepta al menos una cadena.  
**Ayuda para la parte (1): si M1 acepta al menos una cadena, entonces existe al menos una cadena de símbolos 0 y 1, de tamaño n, tal que M1 la acepta en k pasos. Teniendo en cuenta esto, pensar cómo M2 podría simular M1 considerando todas las cadenas de símbolos 0 y 1 hasta encontrar eventualmente una que M1 acepte (¡cuidándose de los casos en que M1 entre en loop!).**  
### <u>CONSULTAR COMO FUNCIONAN LOS "PASOS" EN ESTE CASO YA QUE TENEMOS ADEMAS INFINITAS CADENAS</u>  
![ejercicio5.1](./imagenes/trabajo2-ejercicio5.1.png)

### 2. ¿Se puede construir además una MT M3, utilizando la MT M1, que acepte, cualquiera sea su cadena de entrada, sii la MT M1 acepta a lo sumo una cadena? Justificar.  
### <u>CONSULTAR</u>  
**En este caso podemos suponer que la MT M3 encuentre que MT M1 acepte una cadena, y podria incluso MT M3 rechazar si encuentra que MT M1 acepta 2 cadenas. Pero al trabajar con todas las cadenas (Σ) no podria la MT M3 resolver que MT M1 acepta solo 1 cadena, ni tampoco que la MT M1 no acepte ninguna cadena**

