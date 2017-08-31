# Robot-controls
program which contains the robot controls made whith an arduino


//#include<LiquidCrystal.h>

char buff;

byte EF = 10;    //Esquerda Frente
byte ET = 11;    //Esquerda Tras
byte RE = 3;     //Rele Esquerda
byte DF = 5;     //Direita Frente
byte DT = 6;     //Direita Tras
byte RD = 9;     //Rele Direita

//int lm35 = A0;
//int sensor = A1;
//float umidade;
//float temp;
//int valorLido;
//char velocidade;

//LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

//byte A[8] = {B00110, B01001, B00110, B00000, B00000, B00000, B00000, B00000};

void setup()
{
  Serial.begin(9600);
  //for(int i = 255; i = > 0; i ++)

  pinMode(EF, OUTPUT);
  pinMode(ET, OUTPUT);
  pinMode(RE, OUTPUT);
  pinMode(DF, OUTPUT);
  pinMode(DT, OUTPUT);
  pinMode(RD, OUTPUT);
  
  /*lcd.begin(16, 2);
  lcd.print("Temp:");
  lcd.createChar(1, A);
  lcd.setCursor(8, 0);
  lcd.write(1);
  lcd.setCursor(0, 1);
  lcd.setCursor(0, 0);
  lcd.print("Umid:");*/
}

void loop() // Dica: verificar a tecla pressionada e executar a ação correspondente
{
  /*digitalWrite(RE, HIGH);
  digitalWrite(RD, LOW);*/
  Serial.available() > 0;
  
  while(buff == 'L')
  { 
    digitalWrite(RE, HIGH);
    digitalWrite(RD, LOW);

    
    buff = Serial.read();
    if (buff == 'L') {
      buff == 100;
    }
  }

  
   //right(100);
   //left(100);
   //forward(100);
   //backward(100);
   //while(true);


//**************** ABRE MOTORES ESQUERDA (+B-)***************//

//---------------------Rampa de aceleração (esquerda)-----------------------//
  // Aumenta o valor do mínimo pro máximo com incrementos de 1 em 1
 for (int fadeValue = 0; fadeValue <= 255; fadeValue += 1)
  {
    // Torna o valor da distância de 0 a 255
    analogWrite(EF, fadeValue);
    delay(5);
    analogWrite(ET, fadeValue);
    delay(5);
    analogWrite(DF, fadeValue);
    delay(5);
    analogWrite(DT, fadeValue);

  for (int fadeValue; sqrt(fadeValue * 2);){ // Multiplica o resultado do incremento pelo seu dobro
    }
  }
}
//----------------------------------------------------------------//

//-----------------------Seta para a esquerda---------------------//
 /*void left(int N1) // Início da função 'left'
 {
  // incluir as direcionais no loop   
  // Liga e desliga os relés
  digitalWrite(RE, HIGH);
  digitalWrite(RD, LOW);
  
  analogWrite(EF, N1);
  analogWrite(ET, N1);
  analogWrite(DF, N1);
  analogWrite(DT, N1);

  // Associa a letra L como o botão de comando para o acionamento da seta para a esquerda
  Serial.available() > 0;
  while (buff == 'L')
  { 
    int fadeValue = 0; fadeValue <= 100; fadeValue += 1;
    buff = Serial.read();
    analogWrite(EF, fadeValue);
    delay(5);
    buff = Serial.read();
    analogWrite(ET, fadeValue);
    delay(5);
    buff = Serial.read();
    analogWrite(DF, fadeValue);
    delay(5);
    buff = Serial.read();
    analogWrite(DT, fadeValue);
    delay(5);

    break;
    */
//  }
//}
//-----------------------------------------------------------//

//**************** ABRE MOTORES DIREITA (+A-)******************//

//----------------Rampa de aceleração(direita)------------------//
  // fade in from min to max in increments of 5 points
  /*for (int fadeValue = 0; fadeValue <= 255; fadeValue += 1)
  {
    // sets the value (range from 0 to 255)
    analogWrite(m3, fadeValue);
    // wait for 30 milliseconds to see the dimming effect
    delay(5);
    analogWrite(m4, fadeValue);
    delay(5);
    analogWrite(m1, fadeValue);
    delay(5);
    analogWrite(m2, fadeValue);
    delay(5);
  }

  for (int fadeValue; sqrt(fadeValue * 2);){
  }

//--------------------Seta para a diteita--------------------//
void right(int N1)
{
  digitalWrite(RD, HIGH);
  digitalWrite(RE, LOW);
  delay(1000);

  analogWrite(DF, N1);
  analogWrite(DT, N1);
  analogWrite(EF, N1);
  analogWrite(ET, N1);
}

  Serial.available() > 0;
  while (buff == 'R')
  {
    int fadeValue = 0; fadeValue <= 255; fadeValue += 1;
    buff = Serial.read();
    analogWrite(m3, fadeValue);
    delay(5);
    buff = Serial.read();
    analogWrite(m4, fadeValue);
    delay(5);
    buff = Serial.read();
    analogWrite(m1, fadeValue);
    delay(5);
    buff = Serial.read();
    analogWrite(m2, fadeValue);
    delay(5);

    break;
  }
}*/
//----------------------------------------------------------------//

//****************** FECHA MOTORES DIREITA (+A-)**********************//

//--------------------------- Frente -----------------------------//

//void forward(int N1)


  //int N1;
  //N1 = (forward * 255) / 100   //Escala de 0 a 100
  

  // fade in from min to max in increments of 5 points
  /*for (int fadeValue = 0; fadeValue <= 255; fadeValue += 1)
  {
    // sets the value (range from 0 to 255)
    analogWrite(m3, fadeValue);
    // wait for 30 milliseconds to see the dimming effect
    delay(5);
    analogWrite(m4, fadeValue);
    delay(5);
    analogWrite(m1, fadeValue);
    delay(5);
    analogWrite(m2, fadeValue);
    delay(5);
  }
  for (int fadeValue; sqrt(fadeValue * 2);) {
  }
  Serial.available() > 0;
  while (buff == 'F')
  {
    int fadeValue = 0; fadeValue <= 255; fadeValue += 1;
    buff = Serial.read();
    analogWrite(m3, fadeValue);
    delay(5);
    buff = Serial.read();
    analogWrite(m4, fadeValue);
    delay(5);
    buff = Serial.read();
    analogWrite(m1, fadeValue);
    delay(5);
    buff = Serial.read();
    analogWrite(m2, fadeValue);
    delay(5);
  }

  digitalWrite(RD,HIGH);
  delay(1000);
  
  analogWrite(EF,N1);
  analogWrite(ET,N1);
  
  //analogWrite(EF,N1);
  
  digitalWrite(m3, HIGH);
  digitalWrite(m4, HIGH);
  digitalWrite(RL2, LOW);
  digitalWrite(RL1, LOW);
  digitalWrite(m1, HIGH);
  digitalWrite(m2, HIGH);*/

//---------------------------- Trás ------------------------------//
/*void backward()
{
  // fade in from min to max in increments of 5 points
  for (int fadeValue = 0; fadeValue <= 255; fadeValue += 1)
  {
    // sets the value (range from 0 to 255)
    analogWrite(m3, fadeValue);
    // wait for 30 milliseconds to see the dimming effect
    delay(5);
    analogWrite(m4, fadeValue);
    delay(5);
    analogWrite(m1, fadeValue);
    delay(5);
    analogWrite(m2, fadeValue);
    delay(5);
  }
  for (int fadeValue; sqrt(fadeValue * 2);) {
  }
  Serial.available() > 0;
  while (buff == 'B')
  {
    int fadeValue = 0; fadeValue <= 255; fadeValue += 1;
    buff = Serial.read();
    analogWrite(m3, fadeValue);
    delay(5);
    buff = Serial.read();
    analogWrite(m4, fadeValue);
    delay(5);
    buff = Serial.read();
    analogWrite(m1, fadeValue);
    delay(5);
    buff = Serial.read();
    analogWrite(m2, fadeValue);
    delay(5);
  }
  digitalWrite(m3, HIGH);
  digitalWrite(m4, HIGH);
  digitalWrite(RL2, HIGH);
  digitalWrite(RL1, HIGH);
  digitalWrite(m1, HIGH);
  digitalWrite(m2, HIGH);

}*/
