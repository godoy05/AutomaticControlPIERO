**

## || Teórica a partir de las especificaciones determinando las ecuaciones diferenciales y su programación con Simulink ||

***


1. ***Determinamos las dos ecuaciones que vamos a utilizar:***

 - **Ecuación parte eléctrica:**
	di(t)/dt = 1/L*(V(t)-R(t)-Ea(t)]
 
 - **Ecuación parte mecánica**
	di(t)/dt = 1/J * [Tm(t) - Bw(T)]

 - **Ecuaciones de enlace**
	   
	   Ea(t) = Ka * w(t)
	   Tm = Km *  i(t)
	   Km = Ka = K

2. ***Despejamos los términos de mayor grado.***

3. ***Implementamos las funciones en Simulink***
	
	Utilizaremos dos sumadores, una entrada escalón, dos integradores y  6 ganancias.

  ![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/4d0ab16f-61b0-4576-9a6b-9dfc6e6349b6)

	

4. ***Parámetros motor***

	R = 52Ω
	L = 9,11 * 10^-9 H
	K = 0,0593
	J = 0,0632
	b = 3,19 * 10 ^-9
