# textToSpeechConversion
project on text in pdf to speech conversion
import Pyttsx3 as tts   #importing python text to speech version 3 module named as pyttsx3(before we importing module, have to install it on terminal)
import PyPDF2 as pp #pdf module
from tkinter.filedailog import * 
book = askopenfilename()  #select file 
pdfreader=pp.pdfFileReader(book)
pages=pdfreader.numpages
for num in pages(0,pages):   #for getting all pages, we used looping technique
    page=pdfreader.getPage(num)
    text=page.extractText()    # extract content on page and store in text variable
    audio=tts.init()         #create object 
    audio.say(text)          #converts content in text variable to speech
    audio.runAndWait()       #waits for user input
audio.stop()                 #stops conversion
