# LED-PROJECT

in this project we are going to turn on and turn off led

PROCEDURE TO TURN ON THE LED:

These are the steps we need to follow in order to turn on/off the led

1.first identify the gpio port used to connect the led.in this case we are using the port D(GPIOD)

2.once you indentify the port then select gpio pin where yourgoing tocollect led.here we are using
12th pin of the port D of gpio and each port which consist of 16 pins

3.then activate the peripheral(gpio)
untill you enable the clock for the peripheral.the peripheral is dead and it neither functioning nor
it takes the configaration set by you

once you set the clock the peripheral is ready to take the configartion and the controal related commands
(in stm32f407 microcontroller the peripheral is off by default. we need to enable it)

4.configure the gpio pin mode as output

HOW TO ENABLE THE PERIPHERAL CLOCK

it can be enabled through the periphral clock controal registers of the microcontroller
stm32f407 microcontroller which consist of the RCC(reset clock controal engine)this engine take care of controlling all parts of the clock

by getting the address of the RCC.it is possible to enable the clock
address range of the RCC is 0x40023800-0x40023BFF

take the base address of the rcc and add the offset value
0x40023800+0x30=0x40023830

address of the GpIOd MODE REGISTER and add the offset value
0x40020c00+0x00=0x40020c00

address of the GPIOD OUTPUT DATA REGISTER
0x40020c00+0x14=0x40020c14

By configure these pin using the above memory location address and using the bit wise operator we can turn on/off the led
