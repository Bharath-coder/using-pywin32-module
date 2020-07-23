# using-pywin32-module
Speaks out the data we provided
import requests
import json
def speak(str):
    from win32com.client import Dispatch
    speak = Dispatch("SAPI.SpVoice")
    speak.speak(str)

if __name__ == '__main__':
    url ="https://newsapi.org/v2/top-headlines?country=us&apiKey=dfb466c218674683b99db8fb1d544fbe"
    report =requests.get(url)
    text =report.text
    parsed = json.loads(text)
    speak("Hello Stranger")

    for i in range(0, 5):
        speak("the title is")
        speak(parsed['articles'][i]['title'])
        speak("description is")
        speak(parsed['articles'][i]['description'])

    speak("Thank you for running this code have a nice day")


      
    


    
