# Voice Assistant For Personal Computers
Today almost every Operating System has some sort of voice assistant. For example, Siri, google(the google assistant), and Bixby. Even the windows system has one called Cortona. But we wanted to build a robust voice assistant for windows and Linux which could perform all the rudimentary tasks in the OS.
# Required dependencies:
 ```
  pip install python3 
  pip install time
  pip install beautyfulsoup4
  pip install google
  pip install speechrecognition
  pip install pipwin
  pip install pyaudio
  pip install transformers
  pip install tensorflow
```
# To Execute:
Run the following command:
``` python3 project_voice_recognition.py ```  \
This will execute the file 
(Please install any other dependencies if prompted by the compiler) \
The code will print “talk” then please give the command. \
The code executes inside an infinite while loop, to stop it say “stop” after the “talk” command
and the code will stop. 
# Methodology:
- I first created a voice-to-text algorithm on python using the library Speech_Recognition. 
- For accessing the microphone I used the module speech_recognition. Microphone and to convert the
speech to text, I used google_recognize(), it uses google's free web search API and does not require any
API key. 
- The output of the algorithm is a string of the user's speech. 
- For text segmentation, I required a model which can produce good results without any prior training.
This is because I did not have a dataset for voice commands specifically for Linux Voice assistants.
So the solution to the problem was Zero-Shot Classification(ZSL).
ZSL is a model which can learn from labeled data and predict the classes which were never seen during
the training of the model.
- This model is most useful in this case as I just needed to define certain classes of output and the model
will label the input with the given classes. 
- I used the ZSL model from an online repository- “Hugging face”. Hugging Face is an online community that provides models based on open-source code technologies.
The model used for this project is: [facebook/bart-large-mnli](https://huggingface.co/facebook/bart-large-mnli). 
- Lastly I mapped all the labels of ZSL outputs to the Linux functions using python and the OS library of
python. 
- The OS library is used to implement functionalities like showing the contents of the folder and make a
new directory. 
# Outcomes:
The voice assistant currently can run the following commands:
- Show contents of a file.
- Show today’s date.
- Search for a given keyword on google.
- Make a new directory.
- Simple arithmetic operations.

# Future Goals:
The voice assistant can prove to be a very solid fundamental to a lot of functions and can even be a key to expansion into integration with Internt of Things.
- Including more and more commands for it to be compatible with, aiming to automate close to 90% of standard PC workflows.
