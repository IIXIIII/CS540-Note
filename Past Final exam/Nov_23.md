![img.png](img.png)  
worth case: can reorder the branches  
![img_1.png](img_1.png)
![img_2.png](img_2.png)
![img_3.png](img_3.png)
the heuristics must be admissible to reduce the path. 
h is admissible = h never overestimate the true cost to the goal   
  
s is some state.  
h(s) = heuristic estimate from s to the goal state  
c(s) = optimal cost from s to the goal.   
if question solved, then c(s) will be the one that will be returned.  
  
h admissible = for all states, h(s) <= c(s)  
as long as admissible, returned is optimal, but not necessary optimal.  
ex: when h(s) = 0,  
g(s) = the cost from the start state to s  
Priority: s = g(s) + h(s) = g(s), which is uniform cost search  
so h should be large as possible  
  
Heuristics is consistent/monotone  
<=> 
1. the h(goal) state is 0
2. h(s) <= c(s,n) + h(n)
c for the step cost  
other words, the is true for every neighbor n and the goal state.  

  
h consistent => h admissible  
the opposite is not always true but usually true.  
  
https://pages.cs.wisc.edu/~yw/CS540S24CX3.html
![img_4.png](img_4.png)  
  
 ![img_5.png](img_5.png)  
 IDS  
 ![img_6.png](img_6.png)
 the last one is DFS, 
 ![img_7.png](img_7.png)
 the last round of the IDS is a DFS, so the luckiest case, the last round should be added to the depth of the goal.  
goal check = expansion   
![img_8.png](img_8.png)
Uniform cost search = Dijkstra  

![img_9.png](img_9.png)

c(s) + h(n) expand the one with lower value.  
  
when the heuristic is lower than the actual length of the rought, then A search is called A* search  



![img_10.png](img_10.png)
best first greedy search (run greedy)   
only base on the heuristics  

![img_11.png](img_11.png)



![img_13.png](img_13.png)
![img_12.png](img_12.png)
![img_14.png](img_14.png)

https://pages.cs.wisc.edu/~yw/CS540S24CX4.html


![img_15.png](img_15.png)
![img_16.png](img_16.png)

![img_17.png](img_17.png)






































