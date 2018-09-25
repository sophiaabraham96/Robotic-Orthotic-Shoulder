// Defining PWM pins for motors 1 and 2
#define M1 7
// Defining the pins that will read the analog voltage from the pressure sensor circuit
#define Sensor1 A1
// Defining the pins that will supply the 5V to each presure sensor circuit
#define SV1 40
//Defining the motor driver inputs
#define P1 44
#define P2 45

void setup() 

{
Serial.begin(9600);
//Setting the pins that output 5V to each pressure sensor circuit
pinMode(SV1,OUTPUT);
pinMode(P1,OUTPUT);
pinMode(P2,OUTPUT);
pinMode(M1,OUTPUT);
pinMode(Sensor1,INPUT);
//Calling for the pins to output the maximum voltage from the arduino board (5V)
digitalWrite(SV1,HIGH);
}

void loop() {
// Defining sensitvity range for pressure sensors
//High is just defined as anything greater than the medium range cap
int Zero = 15;
int Low = 600; // From zero to Low
int Medium = 800; // From Low to Medium
//Defining motor speed


int S = 30; // SPEED OF THE MOTOR //


//Defining new variables for the sensor analog output readings
int S1R = analogRead(Sensor1);  

//Analog readings
delay(50);
Serial.println("Sensor 1");
Serial.print(S1R);   

//Calling for the sensor readings to be evaluated in the if-statements

if (S1R < Zero) 
{ digitalWrite(M1,LOW); }

if (S1R < Low && S1R > Zero) 
{ analogWrite(M1,S);
  digitalWrite(P1,LOW);
  digitalWrite(P2,HIGH); }

if (S1R > Low && S1R < Medium) 
{ digitalWrite(M1,LOW); }

if (S1R > Medium)
{ analogWrite(M1,S);
  digitalWrite(P1,HIGH);
  digitalWrite(P2,LOW); }

}