**2021-02-20** : Planning

It's occurred to me that since it's using stepper motors, this thing will need some means of registering endpoints.

I happen to have an MPU-6050 gyroscope/accelerometer module. So how about attaching that to the end of the arm and adjusting the servos until the module says it's in a vertical position..?
https://playground.arduino.cc/Main/MPU-6050/ 

https://www.teachmemicro.com/orientation-arduino-mpu6050/

A simpler means might be to use a mercury tilt switch (which I also have) but I don't know if this could offer enough accuracy.

On a related point, it might be useful when using the arm as a plotter, to have the pen suspended on a spring somehow. When the pen touches the paper it will be pushed up relative to the arm. This could be detected by an IR beam interrupt module - I think I have one of those too. 

**2021-02-17** : Planning

A design that's not bad for a mechanical ballpark is https://www.amazon.it/diymore-Alluminio-Meccanico-Morsetto-MEGA2560/dp/B07FM1VGTV

Stumbled on http://www.jarkman.co.uk/catalog/robots/sketchy.htm which is a https://en.wikipedia.org/wiki/Delta_robot - not what I'm after here, but interesting.