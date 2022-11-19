
import RPi.GPIO as GPIO
#import time
import Adafruit_DHT
sensor = Adafruit_DHT.DHT11
pin = 4
buzzer=18
GPIO.setmode(GPIO.BOARD)
GPIO.setup(buzzer,GPIO.OUT)
while True:
humidity, temperature = Adafruit_DHT.read_retry(sensor, pin)
print(temperature)

if temperature < 30 :
print("under 30")
GPIO.output(buzzer,False)
else:
print("over 30")
GPIO.output(buzzer,True)
