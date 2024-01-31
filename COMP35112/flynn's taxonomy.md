[[COMP35112]]
[wiki](https://en.wikipedia.org/wiki/Flynn%27s_taxonomy)

- proposed in 1966, then extended in 1972, flynn's taxonomy is a classification which has stuck ever since and been used while designing modern processors
![300](https://i.imgur.com/2MwFx60.png)

- SISD: Single Instruction, Single Data
- SIMD: Single Instruction, Multiple Data (vector processors, vector units (MMX,SSE,AVX/AVX2), GPUs)
- MIMD: Multiple Instruction, Multiple Data = Chip Multiprocessors (!)
- SIMD + MIMD = SPMD: Single Program, Multiple Data = Data Parallel machines built from independent processors, but running the same code (however they want)