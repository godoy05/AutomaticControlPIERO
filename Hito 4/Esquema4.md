## Cambio de variable continua a discreta ##

Trabajaremos con variables discretas, por lo que para poder reutilizar los subsistemas antes usados debemos cambiar la variable de continua a discreta.

Este hito se compone de 4 partes:

# 1. H41_1 metro #

<img width="1225" height="516" alt="H41_1 etro" src="https://github.com/user-attachments/assets/2e08785c-fd1e-4928-87cf-c96846c98042" />


Esta compuesto por tres subsistemas:

#  PieroContolado1mZ #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/5b2d3fb8-8b02-49d8-aa0e-07a2700867c2)

Compuesto a su vez por otros dos subsistemas:

# -ControladorPos1mZ #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/6cf01139-1ee8-43d7-b849-ee5f72066b6a)

Donde deberemos cambiar en el controlador PID de variable continua a discreta. Una vez cambiada procedemos a aplicar las condiciones que se nos piden en cada una de las dos ruedas.

- PID sincronizado para rueda izquierda:
  
  ![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/0caf7bf5-7be3-4971-b36d-815584cb8f18)

- PID sincronizado para rueda derecha:
  ![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/28ec579c-47b0-40db-af56-182f38e8af95)

# -GemeloDigitalZ #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/cdadbdcc-8dd2-44da-b789-f51adbf71864)

Compuesto a su vez por dos subsistemas, el PIEROJAJ_HW utilizado anteriormente, y el Piero_ModelZ, donde utilizaremos nuestra función de transferencia en Z.

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/a862f156-a6a6-451b-a70c-f09dafb37f0a)

Esta función de transfrencia en Z la obtendremos de la misma forma que la obtuvimos en anteriormente con la variable continua. Utilizando el System Identification cogemos la función de transferencia con menor error.

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/1ba15a1d-ad97-4954-82bc-a702010e1051)

- Función de transferencia de la rueda izquierda:

  ![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/8b9475ba-7e7d-498e-9342-cc5dfa4465d7)

- Función de transferencia de la rueda derecha:

  ![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/5f9c3f8f-9d24-4faf-afe5-584494afba66)

# MCD #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/e48e5382-1d0e-49a9-939e-3953c417d411)

# Odometría #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/8b8097ec-68eb-426a-8eaf-77703a0a99f8)

Donde vemos la desviación:

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/82f07cbe-924e-428f-a13b-1376f8e6db0e)

# 2. H42_1Circulo #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/b6b557fb-f5f0-427c-a48a-5fe07cfe7612)

Compuesto por los tres subsistemas anteriormente utilizados en H41_1 metro, pero ahora tendremos un nuevo PID externo que tenemos que sintonizar.

- Gráfica del controlador de velocidad angular cumpliendo las especificaciones:
![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/8322abda-3e7b-4ab2-9af7-0e0aaa57a0c7)

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/7a42d342-667d-482b-9caf-25d51e7b319c)

# 3. H43_Giro360 #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/b24de8c1-da6a-40c8-bae8-29f6905f455d)

Odometría:

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/33d043d5-2a2f-49a9-ac8a-83034b7bf1ba)

# 4. H4_Salirclase #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/9075568a-63e7-4408-a3de-70799923369b)

Usaremos dos señales de entrada, una para la velocidad lineal y otra para el ángulo de giro.

Señal para la velocidad lineal (V):

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/ec3ed674-16e3-4da7-b4db-324b3dfb7b48)

Señal para la velociad de giro (Theta):

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/748fe024-d2ae-4397-bd85-17c21a883cd8)

Odometría

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/600e51e3-fe45-432c-94c2-5cc378935c92)

























