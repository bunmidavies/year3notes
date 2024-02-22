[[COMP34212]]

- many of the operations with the naoqi library are asynchronous - in certain cases you may want to wait until some action is complete before you begin the next action

```python
from naoqi import ALProxy
IP = "pepper.local"
PORT = 9559
motion = ALProxy("ALMotion",IP,PORT)
tts = ALProxy("ALTextToSpeech", IP, PORT)
motion.moveInit()
id = motion.post.moveTo(0.5,0)
motion.wait(id, 0)
tts.say("I have walked")
```