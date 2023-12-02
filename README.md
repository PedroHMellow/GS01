#Problema : A falta de cuidado que as pessoas têm consigo mesmas é grande, e um dos motivos para essa negligência pode ser a falta de informação e educação sobre os cuidados com o corpo, como alimentação balanceada e falta de exercícios. Tentar se educar sobre esses assuntos depois de adotar pode ser difícil, afinal, equilibrar estudos e vida é um grande desafio.

Solução: Na soluç~so de edge, abordamos o problema um pouco diferente, onde uma pessoa que tem o imc alto ou um percentual de gordura alto, fica com um dispotivo que monitora seus sinais vitais, conectada de forma remota com o seu celular mostrando se seu colesterol está alto, ou se sua pressão está subindo, assim sendo dessa forma utilizamos o arduino para criar um sensor de movimento que para avisar algum profissional sobre isso, ou seja quando a pressão sobe ou o colesterol está alto ela faz o sensor funcionar apenas passando a mão na frente dele, que solta um alerme de som para avisar o profissional o mais rápido possivel para que medidas sejam tomadas.

LINK DO PROJETO: https://www.tinkercad.com/things/an2ToXLPz9C-copy-of-sensor-de-movimento-20/editel?tenant=circuits


CODIGO FONTE: 

int Sensor;
int Alarme;
int Led;
int Power;
int IV;
int X;

void setup()
{
  
  Power = 2;
  Sensor = 3;
  Led = 4;
  Alarme = 5;
  
  pinMode(Power, INPUT);
  pinMode(Sensor, INPUT);
  pinMode(Led, OUTPUT);
  pinMode(Alarme, OUTPUT);
  
}

void loop()
{
  
  X = digitalRead(Power);
  IV = digitalRead(Sensor);
  
  if (X == LOW) {
    
    if (IV == HIGH) {
      
      TocarAlarme(1);
      
    } else {
      
     noTone(Alarme); 
      
    }
    
  }
  
}

void TocarAlarme(int Y) {
  
  tone(Alarme, 220);
  digitalWrite(Led, HIGH);
  delay(400);
  digitalWrite(Led, LOW);
  delay(400);
  TocarAlarme(2);
  
}
