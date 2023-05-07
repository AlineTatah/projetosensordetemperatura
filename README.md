# projetosensordetemperatura

int celsius = 0;
int sensor = 0;
int motor = 12;

void setup(){
  pinMode(A0,INPUT);
  Serial.begin(9600);
  pinMode(12,OUTPUT);
  pinMode(11,OUTPUT);
  pinMode(10,OUTPUT);
}
void loop(){
  sensor = analogRead(A0);
  celsius = map(((analogRead(A0) - 20) * 3.04),0 ,1023 ,-40 ,125);
  
  Serial.print("Medida do sensor = " );
  Serial.println(sensor);
  Serial.print("Temperatura = ");
  Serial.println(celsius);
 
  if (celsius >= 30 & celsius >=50)
  {
    digitalWrite(12,HIGH);
    digitalWrite(11,HIGH);
    digitalWrite(10,HIGH);
  }
  
  else 
  {
    digitalWrite(12,LOW);
    digitalWrite(11,LOW);
    digitalWrite(10,LOW);
  }
  
}


