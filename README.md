# Choosing Subsets with Maximum Weighted Average
### (Newton Iteration Method)
https://www.ics.uci.edu/~eppstein/pubs/EppHir-TR-95-12.pdf  

### Let $S$ be the set of grade score values and weights of each lesson.
### $S:\{(v_1,w_1),(v_1,w_1),...,(v_n,w_n)\}$  
### $v_i$ score value of lesson $i$
### $w_i$ score weight of lesson $i$

### Let $n$ be the number of elements in $S$, such that $|S| = n$, and $k$ be the number of elements to exclude from the chosen subset.
Suppose that some $(n − k)$-element set $T ⊂ S$ has weighted average at least $A$.  
We can write this as an inequality of the form:
# $A \leq A(T) = \frac{\sum_{i\in T}v_i}{\sum_{i\in T}w_i}$
Assume that all weights are positive, can rewrite as:  
# $\sum\limits_{i\in T}(v_i-Aw_i)\geq 0$

ie. If some $T$ has a weighted average greater than or equal to some value $A$, then $\sum\limits_{i\in T}(v_i-Aw_i)\geq 0$

For each lesson score $i$, define the decreasing linear function:
### $f_i(A)=v_i - Aw_i$
then also define:
### $F(A) = \max\limits_{|T|=n-k}\sum\limits_{i\in T}f_i(A)$
Which can be computed by selecting the $n-k$ largest values of $f_i(A)$ from above
### $F(A)$ is a piecewise linear decreasing function since it is the maximum of ${n \choose n-k}$ decreasing linear functions. Thus we can simply find the root of F(A) using Newton iteration method.
