[[COMP35112]]

- libraries such as [[CUDA programming language|CUDA]]/[[OpenMP]]/[[SYCL]] are not performance portable, due to:
	- optimal grid & block size differing between devices
	- local/global memory tradeoffs varying
	- tilling and unrolling working differently between devices
	- weird performance tricks required across devices for optimal performance

- tuned libraries such as MKL, cuBLAS, cuFFT, cuSPARSE, nvGRAPH, CUTLASS... all provide device-agnostic implementations with high performance
- however, the majority of these libraries provide very specific algorithms, so don't provide you a way to write general algorithms which will perform well across any device