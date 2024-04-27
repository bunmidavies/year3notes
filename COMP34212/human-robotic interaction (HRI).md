[[COMP34212]]

- Human-Robot Interaction (HRI) involves the application of social robotics and language models to scenarios involving the joint collaboration of humans and robots (e.g. factories, education, social companionship)
# HRI Challenges

- technical/scientific challenges: speech recognition/generation, action recognition, intention reading, trust and acceptability ([[trust in human-robot interaction]]), emotion recognition/production, long-term interaction

# speech in robotics

- two main types of application are important:
	- automatic speech recognition systems (ASR)
	- speech synthesis systems (e.g. text-to-speech)
- issues with ASR for children include the fact that child speech is very different from adult speech - their pitch is higher, and they may often utter in ungrammatical ways
- microphone quality can also have significant impact on speech recognition, as well as a number of other factors that are recommended:

![400](https://i.imgur.com/ou9jRIF.png)

# action/pose recognition

- there have been two main revolutions with respect to the recognition of action/poses:
	1. kinect and RGBD cameras (essentially acting as cheap 3D sensors)
	2. deep learning for real-time multi-person keypoint detection in the face, gaze, hands, and feet etc.
- OpenPose is a well known framework for action recognition