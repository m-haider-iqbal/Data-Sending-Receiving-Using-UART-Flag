#include <Arduino.h>

void uartinit();
void dataSending(char data);
void dataReceiving();
char info1;

void setup() 
{
 uartinit();
}

void loop() 
{
  dataReceiving();
  delay(500);
}
void uartinit()
{
UCSR0B = 1 << 4 | 1 << 3;
UCSR0C = 1 << 2 | 1 << 1;
UBRR0 = 103;
}
void dataSending(char data)
{
  UDR0 = data;
  while (!( UCSR0A & 1 << 6));
}
void dataReceiving()
{
  while (!(UCSR0A & (1 << 7)));
  info1 = UDR0;
  dataSending(info1);
}

