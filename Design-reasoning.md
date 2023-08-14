### Choosing devboards over arduino
I don't think an arduino will do. 

At minimum the arduino will need to communicate with a wireless chip ( e.g nrf24l01 or sx1280 ) and an IMU. The arduino has (I believe) only 1 SPI interface and maybe 2 I2C interfaces? It's either going to be pretty slow I2C or you have to share the SPI interface between the wireless chip and the IMU.

For controlling wheels from the arduino you'd need at least 5 timers ( 1 for PWM generation, 4 for capturing the encoders)  and thr arduino only has 3 ( 2x 8 bit, 1x 16 bit). Even controlling just 1 motor is difficult with the 8bit timers.

And then you'd still not have leds, buzzers (more pwm), dribbler (an extra motor), etc. All of that with a 16MHz processor, it will all be very limiting

2
[18:57]
I highly recommend the STM32 Nucleo development boards. They're not that much more expensive than Arduinos. Given that you pick the right one, you'll have enough timers, interfaces, and processing speed (216mhz and higher), and its 32 bit.

We use the stm32f767zit6 and it controls our entire robots.

Additionally it's easy to program using VSCode + the Platformio extension
[19:00]
You could also go even higher and use a Raspberry pi, although they might be a little more expensive. You get the power of an operating system on your robot (simpler programming,  logging of data, a screen, no embedded c) etc. Satisfying your real time requirement might be a bit more difficult though, because, operating system
[19:00]
You could go even higher higher and use eg a Jetson Nano. Even more power, even faster, allows for running neural networks and image recognition and what not. But, its quite expensive
