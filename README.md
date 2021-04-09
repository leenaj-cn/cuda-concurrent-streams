# CUDA-Concurrent-Streams
#performance
```
$ make profile
nsys profile --stats=true --force-overwrite=true -o streams-report ./streams
Warning: LBR backtrace method is not supported on this platform. DWARF backtrace method will be used.
WARNING: The command line includes a target application therefore the CPU context-switch scope has been set to process-tree.
Collecting data...
num_entries: 67108864
TIMING: 86.9552 ms (total time on GPU)
STATUS: test passed
Processing events...
Saving temporary "/tmp/nsys-report-ffff-d962-c1f7-3790.qdstrm" file to disk...

Creating final output files...
Processing [==============================================================100%]
Saved report file to "/tmp/nsys-report-ffff-d962-c1f7-3790.qdrep"
Exporting 1184 events: [==================================================100%]

Exported successfully to
/tmp/nsys-report-ffff-d962-c1f7-3790.sqlite


CUDA API Statistics:

 Time(%)  Total Time (ns)  Num Calls    Average     Minimum    Maximum           Name         
 -------  ---------------  ---------  -----------  ---------  ---------  ---------------------
    41.8        315416188          2  157708094.0       2162  315414026  cudaEventCreate      
    35.7        269762018          1  269762018.0  269762018  269762018  cudaHostAlloc        
    11.5         86459589          8   10807448.6       5194   23276528  cudaStreamSynchronize
    10.7         80659534          1   80659534.0   80659534   80659534  cudaFreeHost         
     0.1           943668          1     943668.0     943668     943668  cudaMalloc           
     0.1           850863          1     850863.0     850863     850863  cudaFree             
     0.0           205123         16      12820.2       6336      42710  cudaMemcpyAsync      
     0.0           116311          8      14538.9       9051      41884  cudaLaunchKernel     
     0.0            81049          8      10131.1       5025      41413  cudaStreamCreate     
     0.0            62698          8       7837.3       6153      16234  cudaStreamDestroy    
     0.0            32268          2      16134.0       8509      23759  cudaEventRecord      
     0.0             7815          1       7815.0       7815       7815  cudaEventSynchronize 
     0.0             5118          2       2559.0       1710       3408  cudaEventDestroy     



CUDA Kernel Statistics:

 Time(%)  Total Time (ns)  Instances   Average    Minimum   Maximum                             Name                           
 -------  ---------------  ---------  ----------  --------  --------  ---------------------------------------------------------
   100.0        134096353          8  16762044.1  10196055  20553485  decrypt_gpu(unsigned long*, unsigned long, unsigned long)



CUDA Memory Operation Statistics (by time):

 Time(%)  Total Time (ns)  Operations   Average   Minimum  Maximum      Operation     
 -------  ---------------  ----------  ---------  -------  -------  ------------------
    51.8         52450950           8  6556368.8  6206432  6960601  [CUDA memcpy HtoD]
    48.2         48880683           8  6110085.4  5347401  7179223  [CUDA memcpy DtoH]



CUDA Memory Operation Statistics (by size in KiB):

   Total     Operations   Average    Minimum    Maximum       Operation     
 ----------  ----------  ---------  ---------  ---------  ------------------
 524288.000           8  65536.000  65536.000  65536.000  [CUDA memcpy DtoH]
 524288.000           8  65536.000  65536.000  65536.000  [CUDA memcpy HtoD]



Operating System Runtime API Statistics:

 Time(%)  Total Time (ns)  Num Calls   Average    Minimum   Maximum            Name         
 -------  ---------------  ---------  ----------  -------  ---------  ----------------------
    56.8        902400969         19  47494787.8    51169  100194710  poll                  
    28.9        458846152        630    728327.2     1571  264037820  ioctl                 
     9.7        154856314         13  11912024.2     1608  154828911  read                  
     4.4         69508030         77    902701.7     2480   66521350  mmap                  
     0.1          1713848         73     23477.4     8234      39353  open64                
     0.0           572481         11     52043.7    30855      85018  pthread_create        
     0.0           297806          8     37225.8    30737      48191  sem_timedwait         
     0.0           236136         24      9839.0     2631      72849  fopen                 
     0.0           221624         15     14774.9     1018      66031  fgetc                 
     0.0           197663          3     65887.7    64412      68560  fgets                 
     0.0           152326         10     15232.6     8865      35895  write                 
     0.0           131824         78      1690.1     1376       2417  fcntl                 
     0.0           103595          3     34531.7    14340      69868  putc                  
     0.0            61309          9      6812.1     3067      11350  munmap                
     0.0            56324         18      3129.1     1994       8257  fclose                
     0.0            49464          5      9892.8     5634      12283  open                  
     0.0            22638          2     11319.0     8480      14158  socket                
     0.0            16034          1     16034.0    16034      16034  sem_wait              
     0.0            14431          5      2886.2     1192       6714  fwrite                
     0.0            14277          1     14277.0    14277      14277  connect               
     0.0             8669          1      8669.0     8669       8669  pipe2                 
     0.0             4355          1      4355.0     4355       4355  bind                  
     0.0             4318          4      1079.5     1027       1136  fflush                
     0.0             4168          1      4168.0     4168       4168  fopen64               
     0.0             2648          1      2648.0     2648       2648  listen                
     0.0             1398          1      1398.0     1398       1398  pthread_cond_broadcast
     0.0             1117          1      1117.0     1117       1117  pthread_mutex_trylock 

Report file moved to "streams-report.qdrep"
Report file moved to "streams-report.sqlite"


```
