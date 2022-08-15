## Avoid sensor

Los sensores infrarrojos para evitar obstáculos son sensores pequeños y económicos que se usan a menudo en robots, y el proyecto Arduino para detectar objetos cerca del sensor. Los sensores infrarrojos funcionan enviando una luz infrarroja con cierta frecuencia y luego detectando si parte de la luz se ha reflejado de regreso al sensor.

### Hardware utilizado en este tutorial:
<ul>
<li>1 x ESP-WROOM-32 Dev Module</li>
<li>1 x Micro USB Cable</li>
<li>1 x Protoboard</li>
<li>3 x Cables macho hembra</li>
</ul>

## Sensor
![](https://github.com/CarlosRuiz02/LaserEmit/blob/main/Laser%20Emit/LaserEmit.png)
## Diagrama
![](https://github.com/CarlosRuiz02/LaserEmit/blob/main/Laser%20Emit/Laser%20Emit%20Diagrama.PNG)


## Código
```c++
int LED = 2;
int isObstaclePin = 4;
int isObstacle = HIGH;

void setup() {
  pinMode(LED, OUTPUT);
  pinMode(isObstaclePin, INPUT);
  Serial.begin(9600);
}

void loop() {
  isObstacle = digitalRead(isObstaclePin);
  if (isObstacle == LOW)
  {
    Serial.println("OBSTACLE!!, OBSTACLE!!");
    digitalWrite(LED, HIGH);
  }
  else
  {
    Serial.println("Clear");
    digitalWrite(LED, LOW);
  }
  delay(200);
}