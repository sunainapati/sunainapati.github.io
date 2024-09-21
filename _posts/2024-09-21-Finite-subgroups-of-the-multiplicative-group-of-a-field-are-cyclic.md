---
layout: post
_title: Finite subgroups of the multiplicative group of a field are cyclic
tags : Number-theory Abstract-algebra 
---
I was trying the following problem from Berkeley problems in mathematics.
<div class="theorem">
  Given $R$ is an integral domain and $G$ is a finite subgroup of $R^{*}$. Show that $G$ is cyclic
</div>

Turns out, we simply consider the field of quotients. And the following statement is true. 

<div class="theorem">
If $G$ is a finite subgroup of the multiplicative group $F^*$ of a field $F$, then $G$ is cyclic.
</div>

We consider the field because then we can use the fact that $F[x]$ is a PID and hence a UFD. I liked this proof in MSE, I will share it here.

<div class="proof">
<div class="lemma">
Let $G$ a finite group with $n$ elements. If for every $d \mid n$,  $\# \{x \in G \mid x^d = 1 \} \leq d$, then $G$ is cyclic. 
</div>
<div class="proof">
  Fix $d \mid n$ and consider the set $G_d$ made up of elements of $G$ with order $d$. Suppose that $G_d \neq \varnothing$, so there exists $y \in G_d$; it is clear that $\langle y \rangle \subseteq \{ x \in G \mid x^d = 1 \}$. But the subgroup $\langle y \rangle$ has cardinality $d$, so from the hypothesis we have that $\langle y \rangle = \{ x \in G \mid x^d = 1 \}$. Therefore $G_d$ is the set of generators of the cyclic group $\langle y \rangle$ of order $d$, so $\# G_d  = \phi(d)$.

We have proved that $G_d$ is empty or has cardinality $\phi(d)$, for every $d \mid n$. So we have:

$$\begin{align}
n &= \# G\\
& = \sum_{d \mid n} \# G_d \\
&\leq \sum_{d \mid n} \phi(d) \\
&= n.
\end{align}$$

Therefore $\# G_d = \phi(d)$ for every $d \vert n$. In particular $G_n \neq \varnothing$. This proves that $G$ is cyclic. QED
</div> 
If $G$ is a finite subgroup of the multiplicative group of a field, then $G$ satisfies the hypothesis because the polynomial $x^d - 1$ has $d$ roots at most.
</div>
