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

The structure corresponding to an instance contains the following fields: 
* .Network is a (sparse) nxm Matrix which represents the incidence matrix of the graph, that is, (v,e) = 1 if the edge e exits vertex v, (v,e) = -1 if it enters v and (v,e) = 0 otherwise (the latter cases, i.e. zero-entries, are not specifically listed in a sparse matrix).  
* .Capacity is a m-dimensional vector consisting of the edge capacities.
* .SourceSink is a 1x2xn Matrix where the matrix SourceSink(:,:,i) yields the \[source,sink\] pair for player i.
* .C1 is a mxmxn Matrix where C1(:,:,i) is the C1 cost matrix of player i (cf. paper).
* .C2 is a mxn Matrix where C2(:,i) is the C2 cost vector of player i (cf. paper; note that in the case of a congestion game, i.e. b = 1, C1(:,:,i) = diag(C2(:,i)) holds in the matlab file which yields the described "congestion game" cost function in the paper for C^{cong} = C1(:,:,i) = diag(C2(:,i))).
* .GNEi for i = 1,...,7 which represents the GNE x=(x_1,...,x_n)=GNEi found by the i-th method in Table 1 of the paper (if the field does not exist, no equilibrium was found). For i=7 (Baron), GNE7=(x,nu) also contains the dual variables corresponding to x.
