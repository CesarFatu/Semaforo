#define LED_ROJO_A 2
#define LED_AMAR_A 3
#define LED_VERDE_A 4

#define LED_ROJO_P 5
#define LED_VERDE_P 6
#define LED_POTE A1
#define PULSADOR 0


int analogPin  = A0;
int POTE; 

void setup() {
  Serial.begin (9600);

  int TIME_ON_R = 5000;
  int TIME_ON_A = 2000;
  int TIME_ON_V = 5000;
  int LECTURA_POTE;
  int MULT = 1;
  int PULSA = 0;
  
  
  pinMode(LED_ROJO_A,OUTPUT);
  pinMode(LED_AMAR_A,OUTPUT);
  pinMode(LED_VERDE_A,OUTPUT);
  pinMode(LED_ROJO_P,OUTPUT);
  pinMode(LED_VERDE_P,OUTPUT);
  pinMode(POTE,INPUT);
  pinMode(PULSADOR, INPUT);

}

void loop() {
  PULSA = digitalRead(PULSADOR);
  Serial.println(PULSA);
 // while (PULSADOR==0)  {
    POTE = analogRead(analogPin);       // realizar la lectura analógica
    //Serial.println(POTE);
    digitalWrite(LED_ROJO_A , HIGH);
    digitalWrite(LED_VERDE_P , HIGH);
    delay(3000);
    digitalWrite(LED_AMAR_A , HIGH);
    digitalWrite(LED_VERDE_P , LOW);
    digitalWrite(LED_ROJO_P , HIGH);
    delay(2000);
    digitalWrite(LED_ROJO_A , LOW);
    digitalWrite(LED_AMAR_A , LOW);
    digitalWrite(LED_VERDE_A , HIGH);
    delay(3000);
    digitalWrite(LED_AMAR_A , HIGH);
    delay(2000);
    digitalWrite(LED_VERDE_A , LOW);
    digitalWrite(LED_AMAR_A , LOW);
    digitalWrite(LED_ROJO_P , LOW);
 // }
//  digitalWrite(LED_ROJO_A , LOW);
//  digitalWrite(LED_AMAR_A , LOW);
//  digitalWrite(LED_VERDE_P , HIGH);
//  delay(7000);

}
