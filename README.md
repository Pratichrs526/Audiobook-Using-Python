# Audiobook-Using-Python
It is an audiobook which is built using python which can extract data from any pdf file and read it for you.


from PyPDF2 import pdf

import pyttsx3

from pyttsx3 import engine

engine= pyttsx3.init()

import PyPDF2

import pywintypes

from tkinter.filedialog import*

book=askopenfilename()
pdfreader= PyPDF2.PdfFileReader(book)
pages=pdfreader.numPages

for num in range(0,pages):
    page=pdfreader.getPage(num)
    text=page.extractText()
    player=pyttsx3.init()
    player.say(text)
    player.runAndWait()
