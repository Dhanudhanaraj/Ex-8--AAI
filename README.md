## NAME:Dhanumalya D
## REGISTER NO:212222230030
## EX.NO:8
## DATE:
# Implementation of Speech Recognition
## AIM:
To implement the conversion of live speech to text.

## ALGORITHM:
### STEP 1:
Import the speech_recognition library.

### STEP 2:
Initialize the Recognizer.

### STEP 3:
Create an instance of the Recognizer class, which will be used for recognizing speech.

### STEP 4:
Set the duration for audio capture.

### STEP 5:
Define a variable to specify the duration (in seconds) for which the program will capture audio from the microphone.

### STEP 6:
Display a message in the console to prompt the user to speak.

### STEP 7:
Capture audio from the default microphone.

### STEP 8:
Use the default microphone as the audio source.

### STEP 9:
Record audio for the specified duration using the Recognizer instance.

### STEP 10:
Perform speech recognition with exceptional handling:
• Attempt to recognize speech from the captured audio using the Google Speech Recognition service.
• If successful, print the recognized text.
• Handle specific exceptions: If the recognition result is unknown or if there is an issue with the request to the Google Speech Recognition service, print corresponding error messages.
• A generic exception block captures any other unexpected errors.

## PROGRAM:
```
import speech_recognition as sr
def record_audio():
    r=sr.Recognizer()
    r.energy_threshold = 6000
    voicedata=''
    try:
        with sr.Microphone() as source:
            audio=r.listen(source)
            voicedata=r.recognize_google(audio)            
    except sr.UnknownValueError:
        print("Unable to Recognize Audio")
    except sr.RequestError:
        print("Unable to find the Resource")
    return voicedata
while True:
    print("Say Something ....")
    text=record_audio()
    print(text)
    if text=="stop" or text=="close" or text=="exit":
        exit(1)
```
## OUTPUT:
![WhatsApp Image 2024-11-15 at 12 49 31 PM](https://github.com/user-attachments/assets/0fea9bb3-1d64-4e2a-9881-082aeb14a18c)


## RESULT:
Thus, the python program for Speech Recognition is implemented successfully.
