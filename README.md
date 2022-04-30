# project-proposal
mini project 

PROJECT TITLE: CONTROLLING SPEED OF MOTOR CONVEYOR BELT USING POTENTIOMETER

ABSTRACT
In our source code, we have initialized the variable V1 and V2 and assigned analog pin A0 for the potentiometer output and 12th Pin for pwm Which means that pin A0 is input and 12 as output.
Now, in void loop (), we are reading the analog value (from A0) using analog Read(pot), and saving it to variable V2. Then, subtract V2 value from 1024 and save the result in V1. Then make the PWM pin 12th of Arduino HIGH and then after a delay of value V1 make that pin LOW. Again, after a delay of value V2 the loop continues.
The reason for subtracting Analog value from 1024 is, the Arduino Uno ADC is of 10-bit resolution (so the integer values from 0 - 2^10 = 1024 values). This means that it will map input voltages between 0 and 5 volts into integer values between 0 and 1024. So if we multiply input analog Value to (5/1024), then we get the digital value of input voltage. Learn here how to use ADC input in Arduino. 
In our circuit, for controlling the speed of DC motor, we use a 100K ohm potentiometer to change the duty cycle of the PWM signal. 100K ohm potentiometer is connected to the analog input pin A0 of the Arduino UNO and the DC motor is connected to the 12th pin of the Arduino (which is the PWM pin). The working of Arduino program is very simple, as it reads the voltage from the analog pin A0. The voltage at analog pin is varied by using the potentiometer. After doing some necessary calculation the duty cycle is adjusted according to it.
For example, if we feed 256 value to the analog input, then the HIGH time will be 768ms (1024-256) and LOW time will be 256ms. Therefore, it simply means the duty cycle is 75%. Our eyes cannot see such high frequency oscillation and it looks like motor is continuously ON with 75% of speed. 
So that’s how we can perform Motor conveyor belt Speed Control using potentiometer and Arduino.


PROBLEM STATEMENT
	
In technology of today we need various machines to perform many tasks easier. One of those machines is motor. For the purpose of transferring a certain object from one place to another, we need conveyor belt to be coupled with motor. The problem is that for the purpose of transferring different objects with different speed categories(e.g.: slow, moderate , fast) we shall need many motors e.g. one for slow conveyor motion, another for moderate conveyor and another for fastest conveyor motion motor. For the solution of those problems we designed multi speed control of conveyor belt which can be used for producing any required speed by varying motor speed using potentiometer.
    



    BLOCK DIAGRAM






#WORKING PRINCIPLE


In our circuit, for controlling the speed of DC motor, we use a 100K ohm potentiometer to change the duty cycle of the PWM signal. 100K ohm potentiometer is connected to the analog input pin A0 of the Arduino UNO and the DC motor is connected to the 12th pin of the Arduino (which is the PWM pin). The working of Arduino program is very simple, as it reads the voltage from the analog pin A0. The voltage at analog pin is varied by using the potentiometer then the speed of motor is controlled.
ARDUINO SOURCE CODE
int pwmPin = 3;
int pot = A0; 
int V1 = 0;
int V2 = 0;

void setup() {
pinMode(pwmPin, OUTPUT); 
pinMode(pot, INPUT);  
}

void loop()
{
V2= analogRead(pot); 
V1= 1024-V2;         
digitalWrite(pwmPin, HIGH); 
delay(V1);
digitalWrite( pwmPin ,LOW);  
delay(V2);  
}



#FRITZING CIRCUIT
 






#CIRCUIT DRAWN IN PROTEUS
 
