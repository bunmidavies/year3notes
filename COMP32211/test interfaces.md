[[COMP32211]]

- since most SoCs are bus-based, this architecture can be exploited and used for testing individual blocks within the SoC that are connected with a specific bus
- if the SoC uses a multi-master bus which reaches many blocks, this exploit then becomes much more effective, and a test interface controller can be implemented and connected to this bus in order to allow external access to many of the chip's functions
- these interface controllers can typically be implemented by loading specific test software onto onboard RAM

![](https://i.imgur.com/wQ9rX3U.png)
