# spi_keyboard_interface
90 keys interface SPI Arduino 

![Screenshot](spi_arduino_interface.jpg)

If you need to scan many buttons with 3 Arduino pins you can use SPI. To read up to 90 keys you can issue these commands:

SPI.beginTransaction(SPISettings(100000, MSBFIRST, SPI_MODE3));
digitalWrite(CS,LOW);

c1 = SPI.transfer(0x00);
c2 = SPI.transfer(0x00);
c3 = SPI.transfer(0x00);
...
digitalWrite(CS,HIGH);//reset
SPI.endTransaction();


CS is the chip select pin. Use whatever you want. Variables c1,c2... map every key in a single bit.
