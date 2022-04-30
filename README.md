# dhtEsp32
<h2>Sensor de Temperatura y Humedad</h2>
<br>
Diagrama de conexión

![diagrama](https://user-images.githubusercontent.com/96139278/166110389-257a8b61-1c80-42f1-8f48-3b132db0428f.jpeg)

Sensor de temperatura y humedad
Boton1: Manual. Activa la refrigeración al ser presionado
Boton2: Alta demanda
Boton3: Sobre carga de funcionamiento

Led1: Refrigeracion manual
Led2: Refrigeración automática

1. Que se encienda la refrigeracion manual cada que se presione el boton de manual
2. La refrigeracion manual tiene prioridad a la refrigeracion automática.
3. Si la termperatura es alta (mayor a 28, por ejemplo), se activa la refrigeracion automática
4. Si tengo alta demanda o sobre carga, se activa la refrigeración automática
5. Si tengo alta demanda o sobrecarga de funcionamiento y ademas temperatura alta, se activan ambas refrigeraciones

Comportamiento
Entradas    B1, B2, B3, Temp (0 cuando temp <= 28, 1 cuando temp > 28)
Salidas     Led1, Led2

B1  B2  B3  Temp  Led1  Led2
0   0   0   0     0     0
0   0   0   1     0     1
0   0   1   0     0     1
0   0   1   1     1     1
0   1   0   0     0     1
0   1   0   1     1     1
0   1   1   0     0     1
0   1   1   1     1     1
1   0   0   0     1     0
1   0   0   1     1     1
1   0   1   0     1     1
1   0   1   1     1     1
1   1   0   0     1     1
1   1   0   1     1     1
1   1   1   0     1     1
1   1   1   1     1     1

Led1 = B3Temp + B2Temp + B1
Led2 = Temp + B3 + B2
