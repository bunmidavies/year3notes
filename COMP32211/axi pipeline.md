[[COMP32211]]

- data can be pipelined within AXI to reduce the distance travelled per clock cycle, and consequently, allow for faster clocking and higher throughput - data can move on every cycle if a pipeline stage can accept and pass on data simultaneously
- AXI pipelines use upstream and downstream signals - a stage will have a 'ready' signal it outputs to the previous stage to let it know if it can currently accept data (upstream), and will also have a 'valid' signal to let the next state know if it is ready to send data (downstream)
- this is much faster than a handshake, where participants would essentially have to wait for one to say 'im ready' then for the other to respond 'im also ready', which basically takes up to 4 clock cycles
![500](https://i.imgur.com/xT99E8N.png)

# single buffer vs double buffer
- in an axi like pipeline, the ideal situation is that data is passed on every clock cycle - if a stage indicates that it is ready, this is a commitment and it must take on the new data
- but if the stage indicates its ready and its not? a blockage is caused and data is ==permanently lost==
![300](https://i.imgur.com/h8BlKEO.png)
- 2 solutions exist to this
	- don't indicate you are ready until no data is held - this is simple to design, however now the pipeline can never be more than half full, thus throughput is reduced ![300](https://i.imgur.com/2fZkAls.png)
	- use 2 flip flops/buffers per pipeline stage, such that you accept new data even if the current data wasn't successfully passed on - now you utilise the full bandwidth of the pipeline, but double your silicon area/resource usage? ![250](https://i.imgur.com/QhmXb8d.png)

