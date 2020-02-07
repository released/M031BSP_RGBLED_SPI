# M031BSP_RGBLED_SPI
 M031BSP_RGBLED_SPI

update @ 2020/02/07

1. Use SPI MOSI (PA0) , to send WS2812 data 

- T1H 1 HIGH 580ns~1μs		target : 0.750 us

- T1L 1 LOW 220ns~420ns		target : 0.375 us

1111 1100 (0xFC)	==> if SPI = 7M

- T0H 0 HIGH 220ns~380ns		target : 0.375 us

- T0L 0 LOW 580ns~1μs			target : 0.750 us

1100 0000 (0xC0)	==> if SPI = 7M	

- RES : more than 280μs

2. upload picture (bit 1 , bit 0) for reference

- bit 1 : ideal high level 0.375x2 us , low level 0.375x1 us

- bit 0 : ideal high level 0.375x1 us , low level 0.375x2 us

![image](https://github.com/released/M031BSP_RGBLED_SPI/blob/master/M031_RGB_1LED_0xFF_0x00_0x00.jpg)

![image](https://github.com/released/M031BSP_RGBLED_SPI/blob/master/scope_bit_High_Low.jpg)

##Scenario : 

1. Default LED pattern will show index state_AllColors in StateMachine function

2. By pressing keyboard from terminal (through UART0 , key from 1 ~ 9 , a ~ d ) to display each LED pattern

