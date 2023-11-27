### :herb: Parallel Programming with Python :herb: <br />

This is the note of the parallel programming with python from Yale Computing Center <br />
[Source](https://github.com/ycrc/parallel_python) <br />
[youtube](https://www.youtube.com/watch?v=AG1soUh4-nU) <br /> <br />

### :women_wrestling: Map Vs Multiprocessing.Process <br />
- Map is running in serial loop with same PID while multiprocessing genereates different processes with different PID. The results of multiprocessing may not be in order of execution.
- The parallel execution has some overhead in setting up the threads so in some cases the time of execution for parallel could be more than serial.

```
Map
```
If the proccesses need to communicate, standard protool called MPI (pyton module mpi4py) can be used. MPI defines how messages are passed between process, including one-to-one and broadcast communication.




:fire: Few definitions :fire:
-----------------------------

:octopus: **COMM**: Communication <br />
:octopus: **RANK**: an ID number given to each internal process to define communication <br />
:octopus: **SIZE**: total number of processes allocated <br />
:octopus: **BROADCAST**: one-to-many communication <br />
:octopus: **SCATTER**: One-to-many data distribution <br />
:octopus: **GATHER**: Many-to-one data distribution <br />
