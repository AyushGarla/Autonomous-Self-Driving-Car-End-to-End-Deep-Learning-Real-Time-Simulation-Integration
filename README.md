Activate env >>> conda create --name myenvirn ////////and >>> activate myenvirn
Keep the trained h5 file in a folder in atom and create a .py file to drive the car based on streeting angles.
Install flask .>>>>conda install -c anaconda flask
Flask is a python micro framework used to build web apps.
Example usage of flask to run website::::::
Write a code in atom in a .py file
from flask import Flask

app = Flask(__name__) #'__main__'

#example----------
#when the user goes to the link /home the function will execute
@app.route('/home')
def greeting():
    return 'Welcome!'

if __name__ =='__main__':
    app.run(port=3000)
Then save and go to the path in anaconda prompt and run the python file.
In the browser go to http://localhost:3000/home.

The goal is to create a bidirectional client server communication [SS1]

Socketio installation:
Then run >>>conda install -c conda-forge python-socketio.
This gives real time communication b/w a server and a client.
When a client creates a single connection to a web server, it helps to keep listening for new events from the server in order to obtain real time communication.
Then install eventlet >>>conda install -c conda-forge eventlet
If this doesn’t work do pip install python-engineio==3.13.2 ////////// and ////////pip install python-socketio==4.6.1 after activating env
Install tensorflow and keras
.>>>conda install -c conda-forge tensorflow
>>>conda install -c conda-forge keras
Then go to atom write a socket io event handler to exchange info between the angles and the car in which frame it is in. The model ‘model.h5’ will predict the steering angle based on which part of the track the car is on
Import 
Install pillow >>>conda install -c anaconda pillow
Convert the images into np array
Preprocess the images same as that in the training using the same preprocessing function defined during the training
Install opencv >>>pip install opencv-python
Make sure that you run the model in the same tensorflow version used for training (I used tf = 2.13.0 and keras = 2.13.1)
Set speed limit = 10 (    throttle = 1.0 - speed/speed_limit #imitially speed =0, 0/anuthing is 0, then as car gains speed and reaches 10, it will be 1 - 10/10 = 0 thus maintaining constant speed.)
We print steering angle, throttle and speed at every step
