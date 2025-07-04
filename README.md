# buildozer_apk
Compile python code to apk file with kivy and buildozer, this is my process in building an android app from python in 2025.

<br>

credits: https://youtu.be/6gNpSuE01qE?si=fo1gIqspaEleucDd

<br>

Example: main.py
```python
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
```
<br>
<pre> numrandom.kv   (filename must be the same as class name)

```
<MyRoot>:
	random_label: random_label

	BoxLayout:
		orientation: "vertical"
		Label:
			text: "RandomNumber"
			font_size: 64
			color: 0.92, 0.45, 0, 1
		Label:
			id: random_label
			text: "-"
			font_size: 64
		Button:
			text: "Gerenate"
			font_size: 32
			size: 100, 50
			on_press: root.generate_number()

```