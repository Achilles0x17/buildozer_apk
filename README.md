# buildozer_apk
Compile python code to apk file with kivy and buildozer, this is my process in building an android app from python in 2025.

main.py
'''python
import kivy
from kivy.app import App
from kivy.uix.boxlayout import BoxLayout
import random

#note that the version should be below 2.3.1
kivy.require('2.3.0')

class MyRoot(BoxLayout):
    
    def __init__(self):
        super(MyRoot, self).__init__()

    def generate_number(self):
        self.random_label.text = str(random.randint(0, 1000))

class NumRandom(App):

    def build(self):
        return MyRoot()

numRandom = NumRandom()
numRandom.run()
'''