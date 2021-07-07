# Design of a Bone Conduction Military Helmet

## Course Project for ME 423 [Machine Design]

***

## Overview

The Travelling Salesman Problem (often called TSP) is a classic algorithmic problem in the field of computer science and  operations  research.  It  is  an  NP-Hard  problem  focused  on optimization.  TSP  has  several  applications  even  in  its  purest formulation,  such  as  planning,  logistics,  and  the  manufacture of  microchips;  and  can  be  slightly  modified  to  appear  as  a sub-problem  in  many  areas,  such  as  DNA  sequencing.  In  this project,  a  study  on  parallelization  of  the Brute  Force  approach (under  several  paradigms)  of  the  Travelling  Salesman  Problem is  presented.  Detailed  timing  studies  for  the  serial  and  various parallel  implementations  of  the  Travelling  Salesman  Problem have  also  been  illustrated.

### Implementations for Different Paradigms of Parallelization


| **Paradigm** | **Tool/Library** | **Implementation** |
| :---: | :---: | :---: |
| Serial | - | `tsp.cpp` |
| Shared Memory | OpenMP | `tsp_omp.cpp` |
| Message Passing | MPI | `tsp_mpi.cpp` |
| Hybrid | MPI & OpenMP | `tsp_hybrid.cpp` |
| GPU Programming | CUDA | `tsp_cuda.cu` | 

### [Project Report](https://github.com/codeknight3/ME766_Project/blob/main/Report.pdf)

### [Presentation](https://github.com/codeknight3/ME766_Project/blob/main/Presentation.pdf)

## Usage

Following are the list of commands to compile \& run the codes for the various implementations mentioned above:

### Serial

```bash
$ g++ tsp.cpp -o tsp    # Compile
$ ./tsp <N>             # Run the code for N cities
```

### OpenMP

```bash
$ g++ -fopenmp tsp_omp.cpp -o tsp_omp   # Compile
$ ./tsp_omp <N> <N_TH>                  # Run the code for N cities using N_TH number of OpenMP threads
```

### MPI

```bash
$ mpic++ tsp_mpi.cpp -o tsp_mpi         # Compile
$ mpirun -np <N_PES> ./tsp_mpi <N>      # Run the code for N cities using N_PES number of MPI processes
```

### Hybrid

```bash
$ mpic++ -fopenmp tsp_hybrid.cpp -o tsp_hybrid     # Compile
$ mpirun -np <N_PES> ./tsp_hybrid <N> <N_TH>       # Run the code for N cities using N_PES MPI processes, each with N_TH OpenMP threads
```

### CUDA
```bash
$ nvcc tsp_cuda.cu -o tsp_cuda  # Compile
$ ./tsp_cuda <N>                # Run the code for N cities
```

***

<p align='center'>Created with :heart: by  <a href="https://github.com/tayalmanan28">Manan Tayal</a> & <a href="https://github.com/AmeyGohil">Amey Gohil</a></p>
