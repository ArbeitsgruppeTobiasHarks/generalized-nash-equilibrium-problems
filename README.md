# GNEPs with Mixed-Integer Variables - Instances of the CDFG 
The file Instances.mat consits of a structure called Instances. 

Each field is another structure representing an instance of the CDFG.

The name of the latter is of the following form: I\_n\_v\_a\_b\_c 

where
* n = 2,4,10 indicates the number of players
* v = 10,15,20 represents the amount of nodes of the graph
* a = ss or a =  mm indicates the single- or multi-source/sink type
* b=1 or b = 10 indicated whether the weights of the player are all set to 1 or randomly set in the range of 1 to 10
* c=1,...,10 (resp. c = 1,...,100 for n = 2, v = 20, a = mm, b = 10) enumerates the instances of the same type. 

The structure corresponding to an instance contains five fields: 
* .Network is a nxm Matrix which represents the incidence matrix of the graph
* .Capacity is a m-dimensional vector consisting of the edge capacities
* .SourceSink is a 1x2xn Matrix where the matrix SourceSink(:,:,i) yields the \[source,sink\] pair for player i
* .C1 is a mxmxn Matrix where C1(:,:,i) is the C1 cost matrix of player i (cf. paper)
* .C2 is a mxn Matrix where C2(:,i) is the C2 cost vector of player i (cf. paper; note that in the case of a congestion game, i.e. b = 1, C1(:,:,i) = diag(C2(:,i)) and C^{cong} = C1(:,:,i) = diag(C2(:,i)))
