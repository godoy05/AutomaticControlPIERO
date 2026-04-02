## Estudio de la zona muerta y de la zona de saturación ##

Utilizaremos el modelo llamado toma datos para determinar tanto la zona muerta como la zona de saturación. El modelo toma datos esta fomrado por un subsistema PIERO_HW, compuesto por otros dos sistemas, el subsistema motores y el encoder.

# Modelo PIERO_HW #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/8a7e3ee8-263c-4c28-b662-f51bae8ee0a9)

# Modelo motores #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/dfad85c2-b7f7-4fa8-b3c5-591c699915f1)

# Modelo del encoder #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/8a137dbc-baf0-4b49-b495-48a5b946dbcc)

# Modelo Toma Datos #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/16336478-b009-42ad-a4d6-4f3f2961dc35)

# Señal rampa usada #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/7c6b57e4-c3ed-401c-a8bb-936f2d247717)

# Scope y tabla de datos obtenida

Observando en el SCOPE, vemos que tiene un retraso en la respuesta, dos picos de saturación tanto por arriba como por abajo y una pequeña inercia al finalizar la respuesta.

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/9645f687-064b-4845-b15f-c18dbecfd242)

En la siguiente imagen se muestra la tabla de los datos obtenidos:

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/9dedd241-a494-4b14-a386-5af6134648da)

Video de la determinación de la zona muerta:

https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/f61d641d-ff20-491e-9659-25afaeca5b31

## Control en Bucle Abierto ##

El contro de bucle abierto hace uso del sistema PIERO_HW, anteriormente usado, y uno nuevo, el ControlBA.

# ControlBA #

Para el controlBA usaremos dos bloques llamados "Lookup with Linear Lagrange Interpolation" que usaremos tanto para la rueda derecha como para la izquierda. Para configurarlo se pincha en el bloque y le damos en el apartado "Edit table and breakpoints", una vez dentro se irá introduciendo valores desde -255 hasta 255 de nuestra tabla de datos.

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/224c1d92-09aa-491a-8524-98e0f4dec0d0)

# Rueda derecha #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/11842e81-995e-435d-9927-9e1ce7ef9e35)

# Rueda izquierda #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/44b3c49f-ec94-49fe-8e01-808a7e4f4032)

## Extraer datos para la identificación a partir de un Pulso ##

Para extraer estos datos volveremos a utilizar el modelo toma datos, pero esta vez utilizando una señal de pulso.

# Toma datos #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/0501fbc7-6a2c-480f-9182-4145c34e4a84)

# Señal de pulso #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/6974783d-ee67-42d5-9c6e-578c32334e55)

Vista desde el SCOPE:

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/b9da6b05-4542-4181-9813-1a8e1b6c63e9)

# Video de como identifico la onda cuadrada #

https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/807fe84d-36cc-46dd-90ea-aaa6c0cf3f9c


Al igual que con la rampa los valores se registran de la misma forma.

## System identification ##

Importamos nuestros para sacar la función de transferencia de nuestro PIERO.

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/c9e8f4f6-ec66-4f16-9be9-437bbfec2272)

Aquí obtendremos nuestras funciones de transferencia, tanto de la rueda izquierda como de la rueda derecha. Vamos probando polos y ceros hasta elegir la mas adecuada. En mi caso he cogido 1 polo y ningún 0 en ambas, pues tenia menor error. Y también ajustamos en la gráfica para eliminar la inercia final.

# Función tranferencia rueda derecha #

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/d5c3083a-1dab-43e2-aae0-370d2970d1b6)

# Función tranferencia rueda izquierda #


![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/53c22b37-924a-4b8d-88b7-637516a9cf1b)


## Gemelo Digital ##

En ultimo lugar crearemos nuestro gemelo digital

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/bd7193ef-7a8d-41f4-8bda-e1ec3444e5eb)

Donde tendremos integrado tambien nuestro subsistema Piero_Model, donde utilizaremos las funciones de tranferencia de ambas ruedas obtenidas anteriormente.

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/8daefcc3-d98e-4368-ba0e-9cda55810c0b)

















