---
layout: post
_title: On application of Tychonoff Theorem
tags : Topology Combinatorics Graph-theory
---
Found this application really cool! I think I might read more about Combinatorial topology.
<div class="theorem">
 If $X_{\alpha}$ is a compact space for each $\alpha$ then product $(\prod_{\alpha} X_{\alpha},\mathscr{T}_{\text{product}})$ is compact. 
</div>
How could an uncountable product be compact????!!!!! I would not prove it here because of the restricted space.
<div class="problem">
Let $G$ be any graph, and $k \in N$. If any finite subgraph of $G$ is $k$-colorable, then $G$ is $k$-colorable.
</div>
Before proceeding further, we introduce a very nice characterization of compact sets. 
<div class="lemma">
 A topological space $X$ is compact $\iff$ for every collection $\mathscr{C}$ of closed sets in $X$ having the Finite Intersection Property (FIP) the intersection, $\bigcap \mathscr{C}$ of all elements of $\mathscr{C}$ is nonempty.
</div>
<div class="proof">
 Assume $\cap_{\mathscr{C}_{\alpha}\in \mathscr{C}}\mathscr{C}_{\alpha}=\varnothing$, then for open subsets of $X$,  $A_\alpha=X\setminus \mathscr{C}_{\alpha}$ we get that $\cup_{\mathscr{C}_{\alpha}\in \mathscr{C}}A_\alpha=X$ by assumption. Since $X$ is compact, we get finite collection $\{\alpha_1,\ldots,\alpha_n\}$ such that $X=A_{\alpha_1}\cup\ldots\cup A_{\alpha_n}$. Again, take compliment, we get that $\mathscr{C}_{\alpha_1}\cap\ldots \cap\mathscr{C}_{\alpha_n}=\varnothing$. Contradicting the Finite Intersection Property. 

 For the other direction, suppose $X$ is not compact. Then $\exists$ a covering of $X$ by open sets such that there is no finite subcover. Say for open subsets $A_\alpha$ of $X$, we have $\cup_{{\alpha}\in I}A_\alpha=X$ such that it has no finite subcover. Define $\mathscr{C}_{\alpha}:= X\setminus A_{\alpha}$ and $\mathscr{C}:=\cup\mathscr{C}_{\alpha}:= \cup X\setminus A_{\alpha}$. 
 Consider any finite number of elements from $\mathscr{C}$, since there is no finite subcover, we get that taking a compliment, $\exists$ an element not in that particular finite subcover, taking complement, we get contradiction to FIP. 
</div>
Now, for the actual proof, intuitively, the whole finite subgraph is $k$-colourable then so is the graph analogous to the FIP. So if we can somehow make the finite subgraphs closed and the space compact we are almost good, which is the intended solution. 
<div class="proof">
 Let $G=(V,E)$ be the graph. Define the space $X=\prod_{v\in V}\{1,\dots,k\}$. Introduce discrete topology in $\{1,\dots,k\}$. Then note that since $\{1,\dots,k\}$ is compact, by tychonoff we get that $X$ is compact with product topology. 
 We define $f_{uv}$ for all $uv\in E$ to be the set of functions $f$ from $V$  to $\{1,\dots, k\}$ such that $f(u)\ne f(v)$. 
 <div class="claim">
  $f_{uv}$ is closed
 </div>
 <div class="proof">
 It is precisely $$\cup_{i\ne j}\pi_{u}^{-1}(i)\cap\pi_{v}^{-1}(j).$$ And we know that they are $\pi_{u}^{-1}(i)$ and $\pi_{v}^{-1}(j)$ are closed and finite union is still closed.
 </div>
 Note, by the assumption, we get that the collection $\{f_e,e\in E\}$ has FIP. So by tychonoff $\cap_{e\in E} f_e\ne \varnothing$. So $G$ is $k$-colorable. Done!
</div>
