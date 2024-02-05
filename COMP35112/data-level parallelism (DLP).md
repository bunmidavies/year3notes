[[COMP35112]]

- data-level parallelism (DLP) refers to parallelism which exists due to structured data, allowing the same/very similar computation to be applied on multiple elements of said structured data
- found in many applications, computation is typically divided into (nearly) equal sized chunks, and DLP will work best when there are no data dependencies between chunks

- example: split vector addition (A+B) into 8 separate chunks which run in parallel
![550](https://i.imgur.com/XB4cbWX.png)


- examples include:
	- matrix multiplication, fourier transform
	- anti-aliasing, texture mapping, illumination/shading
	- differential equations: weather forecasting, simulation, financial modelling