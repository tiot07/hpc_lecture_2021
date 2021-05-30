## 実行手順

```
qrsh -g tga-hpc-lecture -l h_rt=0:10:00 -p -5 -l f_node=1  
module purge
module load gcc cuda/11.2.146 openmpi
mpicxx example.cpp -fopenmp -O3 -march=native
mpirun -np 16 ./a.out
```

##実行結果(最高時)
```
N    : 512                                                                                                          
comp : 0.001508 s                                                                                                  
comm : 0.001227 s                                                                                                 
total: 0.002735 s (98.141932 GFlops)                                                                              
error: 0.000046   
```
