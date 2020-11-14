# final-13-nov
# Write your code here :-)
from microbit import *
from gesture import *
import music
import neopixel
from random import randint
import random
gesture = Gesture()
np = neopixel.NeoPixel(pin1, 30)
names = ["Greetings", "Hello", "Hey" ]
display.scroll(random.choice(names))
display.show(Image.HEART)
sleep(500)
display.show(Image.HEART_SMALL)
sleep(400)
display.show(Image.HEART)
sleep(500)
display.show(Image.HEART_SMALL)
sleep(400)
display.show(Image.HEART)
sleep(500)
display.show(Image.HEART_SMALL)
sleep(400)


np = neopixel.NeoPixel(pin1,30)


tune = ["G5:2", "E5:2", "G5:4", "G5:2", "E5:2", "E5:2", "G5:2", "C6:2","B5:2"]
left = Image("00900:09300:99999:09300:00900")
right = Image("00900:00390:99999:00390:00900")
both = Image("00900:09390:93039:09390:00900")
while True:

    if button_a.is_pressed():
        display.show(left)
    elif button_b.is_pressed():
        display.show(right)
    else:
        display.clear()
    g = gesture.read()
    if g == 'right':
        display.show(Image.HAPPY)
        music.play(music.POWER_UP)
    elif g == 'left':
        display.show(Image.SAD)
        np.clear()
        
        music.play(music.POWER_DOWN)
    elif g == 'up':
        music.play(tune)
    elif g == 'down':
        music.play(tune)
        
    sleep(100)
