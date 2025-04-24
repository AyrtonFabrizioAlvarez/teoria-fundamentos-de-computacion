# Practica 6 Fundamentos de Teoria de la Computacion
## Ejercicio 1. Responder breve y claramente:  
- **a.  Dar un esquema de prueba de la transitividad de las reducciones polinomiales. Ayuda: en clase hicimos lo propio con las reducciones generales.**
  - Si tengo un lenguaje L1, L2 y L3, y existe L1 <=p L2, y L2 <=p L3 ---> seguro existe L1 <=p L3 que es una reduccion polinomial
  - **reduccion:**
    - existe una Mf que es una funcion de reduccion polinomial de L1 a L2
    - existe una Mg que es una funcion de reduccion polinomial de L2 a L3
  - **computabilidad:**
    - Mf transforma w ∈ L1, en una cadena w ∈ L2, ó, Mf transforma w ∉ L1, en una cadena w ∉ L2
    - Mg transforma w ∈ L2, en una cadena w ∈ L3, ó, Mf transforma w ∉ L2, en una cadena w ∉ L3
  - **correctitud:**
    - w ∈ L1, utilizo la composicion g(f(w)), w ∈ L3
    - la composicion de reducciones polinomiales, es una reduccion polinomial `poly(poly(w))`
- **b.  ¿Cuándo un lenguaje es NP-difícil y cuándo es NP-completo?**
  - `NP-difícil`
    - un lenguaje L es NP-dificil si todo lenguage Li ∈ NP, tiene Li <=p L
  - `NP-completo`
    - un lenguaje es NP-completo si:
      - L ∈ NP
      - L ∈ NP-dificil
- **c.  ¿Por qué si P ≠ NP, un lenguaje NP-completo no pertenece a P?**
  - **por el contrareciproco**
    - si un lenguaje L es NPC y L ∈ P ---> P = NP
    - si L es NPC ---> L ∈ NP y existe una reducción polinomial de todo Li ∈ NP a L
    - si L ∈ P ---> todo lenguaje Li ∈ NP tendrían una reducción polinomial a L ∈ P ---> por propiedad de la reduccion ---> P = NP 
    - como se demuestra que el contrareciproco es verdadero ---> se demuestra que si P ≠ NP ---> un lenguaje NPC ∉ P
- **d.  Enunciar el esquema visto en clase para agregar un lenguaje a la clase NPC.** 
  - 1. Probar que L pertenece a NP
  - 2. Construir una reducción polinomial f de Lx ∈ NPC a L -> Lx es un lenguaje NPC conocido
    - por propiedad de la transitividad, todo lenguaje Li ∈ NP que sabemos tiene una reduccion polinomial a Lx (lenguaje NPC ya conocido), si encontramos la reduccion de Lx <=p L, seguro existe la reduccion de Li <=p L
    - al tener una reduccion de Lx <=p L entonces sabemos por propiedad de las reducciones que L es tan o maś dificil que Lx, entonces L ∈ NPC
  - 1)  `L ∈ NPC`
  - 2)  `L1 ∈ NP`
  - 3)  `L <=p L1`
  - 4)  `L1 ∈ NPC`
- **e.  ¿Cuándo se sospecha que un lenguaje de NP está en NPI?**
  - **Asumiendo P ≠ NP**
  - lenguajes que **no cuentan con una MT de tiempo polinomial que los decida.**
  - lenguajes que **no cuentan con una reducción polinomial desde un lenguaje NP-completo.**
 
## Ejercicio 2. Probar:  
- **a.  Si L1 ∈ NPC y L2 ∈ NPC, entonces L1 <=P L2 y L2 <=P L1.** 
  - si `L1 ∈ NPC` sabemos que también `L1 ∈ NP` (propiedad necesaria de L1 para ser NPC)
  - sabemos que `L2 ∈ NPC`
  - sabemos que todo lenguaje NP se reduce polinomialmente a L2 ya que es NPC (propiedad necesaria de L2 para ser NPC)
  - entonces `L1 <=P L2`
  - si `L2 ∈ NPC` sabemos que tambien `L2 ∈ NP` (propiedad necesaria de L2 para ser NPC)
  - sabemos que `L1 ∈ NPC`
  - sabemos que todo lenguaje NP se reduce polinomialmente a L1 ya que es NPC (propiedad necesaria de L1 para ser NPC)
  - entonces `L2 <=P L1`
- **b.  Si L1 <=P L2, L2 <=P L1, y L1 ∈ NPC, entonces L2 ∈ NPC.** **Ayuda: recurrir directamente a la definición de NPC.**  
  - si `L1 ∈ NPC` sabemos que también `L1 ∈ NP` (propiedad necesaria de L1 para ser NPC)
  - si existe `L2 <=P L1` y `L1 ∈ NP` ---> `L2 ∈ NP` 
  - si existe `L1 <=P L2` y `L1 ∈ NPC`---> `L2 ∈ NPC` 


## Ejercicio 3.  Un  lenguaje  es  CO-NP-completo  sii  todos  los  lenguajes  de  CO-NP  se  reducen polinomialmente a él. Probar que SATC es CO-NP-completo. 
**Ayuda: L1 <= L2 sii L1C <= L2C.** 
  - como `SAT ∈ NP` ---> `SATC ∈ CO-NP`
  - todo lenguaje `Li ∈ NP` tiene una reduccion polinomial a `SAT` ---> `SAT ∈ NPC`
  - todo lenguaje `LiC ∈ CO-NP` tiene una reduccion polinomial a `SATC` ---> `SATC ∈ CO-NP-C`
  - como existe `Li <=p SAT`, por propiedad `L1 <= L2 sii L1C <= L2C` ---> existe `LiC <=p SATC`
 
## Ejercicio 4. Sean los lenguajes A y B, tales que A ≠ ∅, A ≠ Ʃ*, y B ∈ P. Probar: (A ⋂ B) ≤P A. 
**Ayuda: intentar con una reducción polinomial que, dada una cadena w, lo primero que haga sea chequear si w ∈ B, teniendo en cuenta que existe un elemento e que no está en A.**   
  - sabemos que, `A ≠ ∅`, `A ≠ Ʃ*`, existe un elemente `e ∉ A`
  - sabemos que, `B ∈ P`, se decide en tiempo poly(n)
  - queremos probar si existe `(A ⋂ B) ≤P A`
    - **reduccion**
      - primero probar si `w ∈ B` y en caso de ser así pasarlo para que se decida en una `Ma` si `w ∈ A`
      - si `w ∉ B` entonces pasa `e` a una `Ma` que sabemos `e ∉ B`
      - `f(w) = w si w ∈ B ó e si w ∉ B`
    - **computabilidad**
      - primero `Mf` simula `Mb` que decide `B`, esto se hace en `O(poly(w))` ya que `B ∈ P`
        - si `w ∈ B` entonces envia en `O(poly(w))` `w` a la `Ma`
        - si  `w ∉ B` entonces envia en `O(poly(e))` `e` a la `Ma`
    - **Correctitud**
      - `w ∈ (A ⋂ B)`
        - `Mf` pasa `w` a `Ma`, si `w ∈ A` ---> `Ma` acepta `w`
      - `w ∉ (A ⋂ B)`
        - `Mf` transforma `w` en `e` y se lo pasa a `Ma` ---> `Ma` rechaza `w`
 
## Ejercicio 5. Sea el lenguaje SH-s-t = {(G,s,t)|G es un grafo no dirigido y tiene un camino de Hamilton del vértice s al vértice t}. Un grafo G = (V, E) tiene un camino de Hamilton del vértice s al vértice t sii G tiene un camino entre s y t que recorre todos los vértices restantes una sola vez. Probar que SH-s-t es NP-completo. Ayuda: se sabe que CH, el lenguaje correspondiente al problema del circuito hamiltoniano, es NP-completo.
  - **primero demuestro que `SH-s-t ∈ NP`**
    - buscar un certificado sucinto verificable en tiempo `poly(n)`, podría ser una lista de aristas con un `CH` entre un vertice `s` y `t` de tamaño `poly(n)` ya que `G = n`
    - para verificar:
      - primero verifico si las aristas del certificado estan presentes en las aristas del grafo G de entrada, asi podemos descartar **si no existe la arista en el grafo G, entonces no es un certificado válido**, esto se hace en `O(|E|^2)` ---> `O(poly(n^2))`
      - segundo verifico por cada vértice de mi grafo G, que no se encuentre repetido en distintas aristas del certificado (para asegurar el `CH`), y verifico si efectiamente la primera arista del certificado empieza con el vértice `s` y termina la última arista con el vértice `t`, todo esto se hace en `O(|V| * |E|)` ---> `O(poly(n^2))`
      - la verificacion completa queda en `O(n^2)` siendo `n = G`
  - **segundo demuestro que existe `CH <=p SH-s-t`**
    - VER EL REPO DE `JOACO`