import speech_recognition as sr
import pyttsx3
import pywhatkit
import datetime
import os
import wikipedia
from AppOpener import open

listener=sr.Recognizer()
engine=pyttsx3.init()
voices=engine.getProperty('voices')
engine.setProperty('voice',voices[1].id)
def take_command():
    try:
        print("How can i help you")
        engine.say("how can i help you")
        engine.runAndWait()
        with sr.Microphone()as source:
            print("listening")
            voice=listener.listen(source)
            command=listener.recognize_google(voice)
            command=command.lower()
            if "alexa" in command:
                command=command.replace("alexa"," ")
            return command    
                
    except:
        pass
        
def run_alexa():
        command = take_command()
        try:
            if 'play' in command:
                    song=command.replace("play"," ")
                    engine.say("playing"+song)
                    print("playing"+song)
                    engine.runAndWait()
                    pywhatkit.playonyt(song)
            elif 'what is your name' in command:
                engine.say("thank you for asking ! my name alexa ,you can call me alexa")
                engine.runAndWait()
            elif 'open'or 'start' in command:
                if "open" in command:
                    command=command.replace("open"," ")
                if "start" in command:
                    command=command.replace("start"," ")
                    engine.say("Opening"+command)
                    engine.runAndWait()
                    open(command)
            elif 'time' in command:
                time=datetime.datetime.now().strftime('%H:%M:%S')
                print(time)
                engine.say("The cuurent time is "+time)
                engine.runAndWait()
            elif 'set alaram' or "reminder" in command:
                os.system('clear')
                engine.say("Enter the hour")
                engine.runAndWait()
                with sr.Microphone()as source:
                    voice=listener.listen(source)
                    alaram=listener.recognize_google(voice)
                    engine.say("Enter the Minute")
                    engine.runAndWait()
                    alaramM=listener.recognize_google(voice)
                    engine.say("am or pm")
                    engine.runAndWait()
                    ampm=listener.recognize_google(voice)
                    ampm=ampm.lower()
                    engine.say("set a message")
                    engine.runAndWait()
                    message=listener.recognize_google(voice)
                    message=alaramM.lower()
                    os.system('clear')
                    print("Alarm as been set ",alaram,alaramM,ampm)
                    if(ampm=="pm"):
                        alaram=alaram+12
                    while(1==1):
                        if(alaram==datetime.datetime.now().hour and
                          alaramM==datetime.datetime.now().minute):
                            engine.say(message)
                            engine.runAndWait()

                            break
                        else:
                             pass
            elif 'wikipedia' in input1:
                    print("From wikipedia")
                    engine.say("From wikipedia")
                    engine.runAndWait()
                    info=wikipedia.summary(command,1)
                    print(info)
                    engine.say(info)
                    engine.runAndWait()
            elif 'in google' in command:
                    print("From google")
                    engine.say("From google")
                    engine.runAndWait()
                    pywhatkit.search(command)
        except:
            pass

run_alexa()
