Let's take an example that has multiple resource requirements for every Process. Let there be three Processes P1, P2, P3, and 4 resources R1, R2, R3, R4. The maximum resource requirements of the Processes are shown in the below table.

|Process|R1|R2|R3|R4|
|---|---|---|---|---|
|P1|3|2|3|2|
|P2|2|3|1|4|
|P3|3|1|5|0|

A number of currently allocated resources to the processes are:

|Process|R1|R2|R3|R4|
|---|---|---|---|---|
|P1|1|2|3|1|
|P2|2|1|0|2|
|P3|2|0|1|0|

The total number of resources in the System are :

|R1|R2|R3|R4|
|---|---|---|---|
|7|4|5|4|

We can find out the no of available resources for each of P1, P2, P3, P4 by subtracting the currently allocated resources from total resources.

Available Resources are :

|R1|R2|R3|R4|
|---|---|---|---|
|2|1|1|1|

Now, The need for the resources for the processes can be calculated by :

Need = Maximum Resources Requirement - Currently Allocated Resources.

The need for the Resources is shown below:

|Process|R1|R2|R3|R4|
|---|---|---|---|---|
|P1|2|1|0|1|
|P2|0|2|1|2|
|P3|1|1|4|0|

The available free resources are <2,1,1,1> of resources of R1, R2, R3, and R4 respectively, which can be used to satisfy only the requirements of process P1 only initially as process P2 requires 2 R2 resources which are not available. The same is the case with Process P3, which requires 4 R3 resources which is not available initially.

The Steps for resources allotment is explained below:

1. Firstly, Process P1 will take the available resources and satisfy its resource need, complete its execution and then release all its allocated resources. Process P1 is initially allocated <1,2,3,1> resources of R1, R2, R3, and R4 respectively. Process P1 needs <2,1,0,1> resources of R1, R2, R3 and R4 respectively to complete its execution. So, process P1 takes the available free resources <2,1,1,1> resources of R1, R2, R3, R4 respectively and can complete its execution and then release its current allocated resources and also the free resources it used to complete its execution. Thus P1 releases <1+2,2+1,3+1,1+1> = <3,3,4,2> resources of R1, R2, R3, and R4 respectively.
    
2. After step 1 now, available resources are now <3,3,4,2>, which can satisfy the need of Process P2 as well as process P3. After process P2 uses the available Resources and completes its execution, the available resources are now <5,4,4,4>.
    
3. Now, the available resources are <5,4,4,4>, and the only Process left for execution is Process P3, which requires <1,1,4,0> resources each of R1, R2, R3, and R4. So it can easily use the available resources and complete its execution. After P3 is executed, the resources available are <7,4,5,4>, which is equal to the maximum resources or total resources available in the System.
    

So, **the process execution sequence in the above example was <P1, P2, P3>**. But it could also have been <P1, P3, P2> if process P3 would have been executed before process P2, which was possible as there were sufficient resources available to satisfy the need of both Process P2 and P3 after step 1 above.