import RPi.GPIO as GPIO
import time
sensor=16
buzzer=18
GPIO.setmode(GPIO.BOARD)
GPIO.setup(sensor,GPIO.IN)
GPIO.setup(buzzer,GPIO.OUT)
GPIO.output(buzzer,False)
print("IR sensor Ready")
while True:
if GPIO.input(sensor):
GPIO.output(buzzer,True)
print("IR sensor Ready")
else:
GPIO.output(buzzer,False)
print("IR sensor not Ready")
