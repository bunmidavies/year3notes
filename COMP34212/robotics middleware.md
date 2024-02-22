[[COMP34212]]

> robotic middleware is designed to manage the complexity and heterogeneity of the hardware and applications, promote the integration of new technologies, simplify software design, hide complexity of low-level communication and the sensor heterogeneity of the sensors, improve software quality, reuse robotic software infrastructure across multiple research efforts, and to reduce production costs

- robotics middleware considers application and hardware elements as nodes, which are connected by middleware infrastructure

# example: ROS

- Robot Operating System (not an actual operating system) is one of the most widespread robotics middleware projects, and is open source with documentation supported by the community
- one of the main communication mechanisms is through ==topics==
- nodes publish on topics which are read by subscriber nodes - for instance, a camera node publishes images to a specific topic, essentially streaming it
- other communication mechanisms exist e.g. on-demand "services"

![](https://i.imgur.com/OCdpEkN.png)


# example: YARP

- Yet Another Robot Platform is a similar middleware to ROS, using a publisher/subscriber model
- the middleware is more C++ specific and tailored to certain robots (e.g. iCub), with a smaller community

# example: NAOqi

- proprietary software of SoftBank robotics, used for all their robots i.e. [[softbank PEPPER robot|PEPPER]], Nao, Romeo
- interfaces exist in python and c++