---
layout: post
_title: Some Problems in Olympiad Graph theory
tags : Olympiad-Graph-theory
---

I recently took a class at the European Girls' Mathematical Olympiad Training Camp 2024, held at CMI. Here are a few problems that I discussed! My main references were Po-Shen Loh's Graph theory Problem set (2008), Adrian tang's Graph theory problem set (2012) and Warut Suksompong's Graph Cycles and Olympiad Problems Handout and AoPS. I also referred to Evan Chen's Graph theory Otis Problem set for nice problems!

# Contents
{:.no_toc}

* A markdown unordered list which will be replaced with the ToC, excluding the "Contents header" from above
{:toc}

# Text Book Problems which are decent 

<div class='problem'>
A connected graph $G$ is said to be $k$-vertex-connected (or $k$-connected) if it has more than $k$ vertices and remains connected whenever fewer than $k$ vertices are removed.
Show that every $k$-connected graph of order atleast $2k$ contains a cycle of length at least $2k$.
</div>
<div class='proof'>
We begin with a lemma.
<div class='lemma'>
 Prove that a graph $G$  of order $n \geq 2k$ is $k$ connected then every 2 disjoint set $V_1$ and $V_2$ of $k$ distinct vertices each, there exist $k$ pairwise disjoint paths connecting $V_1$ and $V_2$
</div>
Actually the lemma is an iff condition.
<div class='proof'>
If not, then pick any disjoint vertices in the path. It will be less than $k$ and disconnects the graph. Which contradicts the $k$ connectedness.
</div>
Let $k \ge 2$. As $G$ is $k$-connected, it is connected and by problem $2$, it must contain a cycle. Consider a maximal cycle $C$. If $|C|\ge 2k$ we are done. Again, by problem $2$, the cycle's lenght is atleast $k$. Also, note that each vertex has degree atleast $k$. 
So, there is $v\in G/C$. Consider $A=N(v)$ ( neighbour of $v$) and $B=C$. There are atleast $k$ disjoint path between $A$ and $B$. By pigeonhole principle, $\exists$ two vertices in $A$ say $v_1,v_2$ which have distinct path to $C$. So we get a bigger cycle, $v-v_1-P_{v_1,C}-C-P_{v_2,C}-v_2-v$, where $P_{v_i,C}$ denotes the path from $v_i$ to $C$ which is distinct.
</div>
<div class='remark'>
 This is a nice result which uses a lot of new ideas. Constructing a bigger cycle is actually a very useful and intuitive idea.
</div>

<div class='problem'>
If every vertex of an undirected graph $G$ has at least $d \ge 2$ neighbors,
then $G$ contains a cycle of length at least $d$.
</div>
<div class='proof'>
 Start with any vertex $v$. Since each vertex has degree atleast $d$, we get that $\exists v_1$ such that $v$ is adjacent to $v_1$. Similarly, since degree $d\ge 2$, there exists a vertex $v_2\ne v$ such that $v_2$ is adjacent to $v_1$. Continue this process. We will get a path $v-v_1-\dots-v_{d}$. Note that if there is no other new vertex $v_{d}$ is adjacent to then it is adjacent to $v$ and hence we get a $d$ lenght cycle. If not then $v_{d}$ is adjacent to a vertex $v_{d+1}\ne v,\dots, v_{d-1}$. Now, look at $v_{d+1}$ and consider $v_1,\dots, v_{d}$. Note that if there is no other vertex apart from the above vertices to which $v_{d+1}$ is neighbour of then consider $v_1-\dots-v_d-v_{d+1}-v_1$ which is a $d$ lenght cycle. Else, $v_{d+1}$ is adjacent to $v_1$ ( so we get a $d+1$ cycle) or it is adjacent to a new vertex. 
 Continue this process. Eventually it has to stop as the graph is finite. And we will be done!
</div>
<div class='remark'>
 So the idea here was to continue adding more and more and more vertices whenever we can. So in a sense, this is a greedy problem. The idea also comes from BFS because in a sense we are trying to go as much depth as we can. 
</div>
<div class='problem'>
 Prove that the sum of all of the degrees is equal to twice the number of edges. Deduce that the number of
odd-degree vertices is always an even number.
</div>
<div class='proof'>
 Let G be a graph with $'e'$ edges and $'n'$ vertices $v_1,v_2,v_3,...,v_n$. Since each edge is incident on two vertices, it contributes $2$to the sum of degree of vertices in graph $G$. Thus the sum of degrees of all vertices in $G$ is twice the number of edges in $G$. Hence, $$\sum_{i=1}^n\text{degree}(v_i)= 2e.$$
The second part follows by parity. 
</div>
<div class='remark'>
 A very simple result in Graph theory but the idea ( which is double counting) is pretty useful! Keep it in mind!
</div>
<div class='problem'>
 Prove that every tree contains a vertex of degree exactly $1$
</div>
<div class='proof'>
 Follows from the problem $2$.
</div>
<div class='remark'>
Note that by problem $3$, there will be atleast $2$ vertices with degree exactly $1$.
</div>

<div class='problem'>
The diameter of a connected, undirected graph $G = (V, E)$ is the length (in number of edges)
of the longest shortest path between two nodes. Show that if the diameter of a graph is $d$ then there is some set $S \subset V$ with $|S| \le n/(d - 1)$ such that removing the vertices in $S$ from
the graph would break it into several disconnected pieces.
</div>
<div class='proof'>
 I do not know why I added this in the set, but here we go. It uses the menger's theorem's max-cut- min-flow version. 
 <div class='lemma'>
  Let $G$ be a finite undirected graph and $x$ and $y$ two nonadjacent vertices. Then the theorem states that the size of the minimum vertex cut for $x$ and $y$ (the minimum number of vertices whose removal disconnects $x$ and $y$) is equal to the maximum number of pairwise vertex-independent paths from $x$ to $y$.
 </div>
So, take $x$ and $y$ such that they are diameter. So $d(x, y) = d$.  Let $k$ be the minimum number of vertices whose removal disconnects $x$ and $y$.  

By Menger's theorem, there are $k$ vertex disjoint paths from $x$ to $y$. Note that each path contains at least $d - 1$ distinct vertices. So the number of vertices of $G$ is $n \geq k(d - 1) = |S|(d - 1)$.  So, $|S| \leq \frac{n}{d-1}$ and $S$ disconnects $G$.

</div>

<div class='problem'>
Let $G$ be a regular bipartite graph (that is, a graph with
all the vertices having the same degree). Prove that $G$ has a perfect matching.
</div>
<div class='proof'>
 We use hall's theorem here. Let the vertex set be $X$ and $Y$.
Every edge with an endpoint in $A$ has an endpoint in $N(A)$, let $E_A$ and $E_{N(A)}$ denote the respective edge sets. 

Then since $G$ is $k$-regular ($k$ is the degree of each vertex), $|E_A| = k |A|$ and $|E_{N(A)}| = k |N(A)|$. But $E_A \subseteq E_{N(A)}$, hence $|A| \leq |{N(A)}|$. By Hall’s theorem there is a complete matching. 

But note that The number of edges from $X$ to $Y$ is $k|X|$ and the number of edges from $Y$ to $X$ is $k|Y|$. As $G$ is bipartite we have $k|X|=k|Y|$. So every vertex in $Y$ is also matched to a vertex in $X$, which together match every vertex in the graph. Thus the complete matching is a perfect matching. 
</div>
<div class='remark'>
 Again, double counting helped a lot! Hall's is also something we should keep in mind. 
</div>

<div class='problem'>
 We define the Ramsey Number $R(s, t)$ to be the minimum integer $n$
for which every red-blue coloring of the edges of $K_n$ contains either a completely red $K_s$ or a completely
blue $K_t$. Prove that $R(s, t)\le \binom{s+t-2}{s-1}$.
</div>
<div class='proof'>
 Note that $R(s, t) \ge R(s-1, t)+R(s, t-1)$, because if we have that many vertices, then when we select one vertex, then it will atleast have $\ge$ $R(s-1, t)$ red neighbors or $\ge$ $R(s, t-1)$
blue neighbors, so we will have red $K_s$ or a blue $K_t$. By induction, we get $$\binom{s-1+t-2}{s-2}+\binom{s+t-1-2}{s-1}=\binom{s+t-2}{s-1}$$
</div>

<div class='problem'>
 If $G$ is a connected, planar, simple graph, then $E \le 3V - 6$.
</div>
<div class='proof'>
 We begin with another double counting argument which is used a lot! 
 <div class='lemma'>
  For a planar graph $G = (V, E)$, $3f \leq 2|E|$ where $f$ is the number of faces in the planar drawing of $G$.
 </div>
 <div class='proof'>
 Each face has at least $3$ edges, and each edges is in (at most) $2$ faces as planar.
 </div>
 By Euler's formula, $f = 2 - |V| + |E|$. Thus, 
        \begin{align*}
                 3f = 6 - 3|V| + 3|E| &\leq 2|E| \\
                 3|E| - 2|E| &\leq 3|V| - 6 \\
                 |E| &\leq 3|V| - 6 \: 
         \end{align*}

</div>
<div class='remark'>
 I have not seen this criterion being used in olympiad problems but the double counting argument is simple and nice.
</div>

<div class='problem'>
 Prove that a graph is bipartite if and only if it has no odd cycles.
</div>
<div class='proof'>
If $G$ is bipartite with vertex sets $V_1$ and $V_2$. If there is an odd cycle, then there must be an edge between two vertices of the same vertex set. 
Conversely, suppose that every cycle of $G$ is even. Then  We consider the following algorithm.
<div class='code'>
 -  pick a vertex ( say $v$) and colour it red.
   
 -  consider all the vertices $v$ is adjacent to and colour them blue
   
 -  consider all the blue vertices and consider all the vertices adjacent to the blue vertices and colour them red
   
 -  consider all the red vertices and consider all the vertices adjacent to the red vertices and colour them blue
   
 -  repeat step $3$ and $4$ untill all vertices are coloured
</div>

Note that this will give a valid colouring ( red vertices will be one vertex set and blue vertices will be another vertex set). We will not get any ambiguous colouring because then it would imply that there is some odd cycle. 
</div>
<div class='remark'>
 This is a very simple yet powerful result. Most of the times the bipartite graph is hidden in the problem. But once you recognise that there are only even cycles, life becomes easier!
</div>

<div class='problem'>
Prove that every connected graph contains a spanning tree
</div>
<div class='proof'>
 Besically whenever you see a cycle, remove one edge. It would keep the graph connected but decrease the number of edges. This process will terminate and we will get our spanning tree. 
</div>
<div class='remark'>
 The idea to find a cycle and remove only $1$ edge is pretty common.
</div>

# Olympiad Problems
<div class='problem'>
Let $n$ be a positive integer. Prove that the edges of the complete graph on $n$ vertices can be
decomposed into $n - 1$ paths of lengths $1, 2, \dots , n - 1$.
</div>
<div class='proof'>
We begin with following lemma. 
<div class='lemma'>
 Show that $K_n$, $n$ is even can be decomposed into  $\frac{n}{2}$ disjointed Hamiltonian paths on edges.
</div>
<div class='proof'>
If the vertices are numbered $0, 1, \dots, 2k-1$ modulo $2k$, where $2k=n$, then the $i^{\text{th}}$ Hamiltonian path is
$$
   (i, i+1, i-1, i+2, i-2, i+3, i-3, \dots, i + (k-1), i - (k-1), i+k).
$$ 
<div class='lemma'>
 $K_n$ for odd $n$ is disjoint union of Hamiltonian cycles. 
</div>
<div class='proof'>
First consider then $n-1$ vertices and decompose the $K_{n-1}$ graph into disjoint union of hamiltonian paths. Now, from the $n$th vertex( say $v$), consider the cycle $xPx$. Essentially connecting the end points with $v$ and forming a cycle. 
</div>
In both cases, we can seperate the cycle into paths of lenght $i, n-i$ for odd $n$ and for $n$ even, seperate the paths into $i,(n-1)-i$ and $n-1$. So done.
</div>


</div>
<div class='remark'>
 The fact that $K_n$ can be decomposed was the crucial hint. Essentially induction worked though!
</div>

<div class='problem'>[IMO 1991]
Let $G$ be a connected graph with $m$ edges. Prove that the edges can be labelled
with the positive integers $1, 2, \dots , m$ such that for each vertex with degree at least two, the
greatest common divisors amongst the labels on the edges incident to this vertex, is $1$.
</div>
<div class='proof'>
Consider  longest possible tour in the graph. Lable the edges in the tour from $1,\dots k$ in that order. Note that except the end points, all other vertex in the tour have edges such that gcd is $1$. If not all edges are covered, repeat the same process again. Note that since we consider longest path, there is no edge adjacent to the endpoints. Continue this process. 
</div>
<div class='remark'>
 Atleast, after doing so many algorithm problems, I do think very algorithmically. So while seeing this problem, thinking greedily helps!
</div>

<div class='problem'>[Iran MO]
 Let $n\ge 3$ be a positive integer. Let G be a grid whose entries are all $0, 1$ or $-1$
such that each row and each column contains exactly one $1$ and one $-1$. Prove that the rows
and the columns of the grid can be re-ordered such that the resulting grid is the negative of $G$. 
</div>
<div class='proof'>
Consider a directed graph $G$ whose vertices correspond to the rows of the table. For each column, add an edge to $G$ pointing from the row in which the column has a $1$ to the row in which the column has a $-1$. Note that this graph will be composed of disjoint directed cycles. Now, consider the graph $G'$ in which all the edges are fliped. The matrix corresponding to this graph $G'$ is negative of the grid.
Consider the cycle $v_1-v_2-\dots-v_k-v_1$. We switch rows corresponding to $v_2,v_k$, $v_3,v_{k-1}$ and so on. And then we switch columns corresponding to $v_2,v_k$, $v_3,v_{k-1}$ and so on. So we have flipped the cycle. And hence we get negative of the graph.
</div>
<div class='remark'>
 Whenever I see a grid, I now think of graphs! (Thanks to network flows). Here we had a matrix with $1,-1,0$ as coefficients. So directed graphs were the first thing to think of! Here the disjoint cycles idea was pretty useful!
</div>

<div class='problem'>[Canada 2006]
 In a rectangular array of nonnegative real numbers with $m$ rows and $n$ columns,
each row and each column contains at least one positive element. Moreover, if a row and a
column intersect at a positive element, then the sums of their elements are the same. Prove
that $m = n$.
</div>
<div class='proof'>
 Consider bipartite graph $G$ with vertex sets $R,C$. $R$ is the row set with $m$ vertices being the $m$ rows and $C$ is the column set with $n$ columns being the $n$ vertices. Make edge $r_i$ between $c_j$ if the entry at $(i,j)$ is positive. 
 Consider any sub-vertex set of $R$. Let it be $X$. Consider $N(W)$. Note that $$\forall c_i\in N(X)\exists r_j\in X\text{ such that } r_jc_i\in G.$$ Since each row has atleast one postive element, every $$r_i\in X\exists c_j\in N(X)\text{ such that } r_ic_j\in G.$$
 This satisfies hall condition. So $m\le n$. Similarly $n\le m$. And we get $n=m$.

</div>
<div class='remark'>
 I think whenever we have a grid, it is nice to intepret it in graphical way. Note that the condition that every row and column has a positive element is needed in order to say $m\le n$.
</div>

<div class='problem'>[Iran 2005]
  Each edge of a tournament is coloured red or blue. Prove that there exists a
vertex $v$ in the tournament such that for every other vertex $w$, there exists a directed path
from $v$ to $w$ of the same colour.
</div>
<div class='proof'>
Say $T$ is a minimal counterexample. Then, for each vertex $x$ of $T$ we can choose a vertex $f(x)\ne x$ such that there is a monochromatic path from $f(x)$ to every vertex of $T-x$ but there is no monochromatic path from $f(x)$ to $x$. We can say this because of minimality. Note there is edge $x\to f(x)$ as tournament. So there is a cycle $x_1,\dots,x_n,x_1$ such that $f(x_i)=x_{i+1}$ for $i=1,2,\dots,n-1$, and $f(x_n)=x_1$. 

If the edges $x_1x_2,x_2x_3,\dots,x_nx_1$ are the same color, we get contradiction as there is monochromatic path from $x_2$ to $x_1$, but there is edge from $x_1$ to $x_2$. This contradicts minimality. Therefore the cycle must contain two consecutive edges of different colors. WLOG say  $x_1x_2$ is red and $x_2x_3$ is blue.

Now there is a monochromatic path from $x_3$ to $x_1$. If there is a red path from $x_3$ to $x_1$, then there is a red path from $x_3$ to $x_2$. Contradiction as there is no monochromatic path from $x_3$ to $x_2$. if there is a blue path from $x_3$ to $x_1$, then there is a blue path from $x_2$ to $x_1$. Contradiction.
</div>
<div class='remark'>
 In general, taking extremal cases helps a lot! They simplify things a lot more!
</div>
<div class='problem'>[2017 ISL N3]
Determine all integers $ n\geq 2$ having the following property: for any integers $a_1,a_2,\ldots, a_n$ whose sum is not divisible by $n$, there exists an index $1 \leq i \leq n$ such that none of the numbers$$a_i,a_i+a_{i+1},\ldots,a_i+a_{i+1}+\ldots+a_{i+n-1}$$is divisible by $n$. Here, we let $a_i=a_{i-n}$ when $i >n$. 
</div>
<div class='proof'>
 Note, if $n$ is composite, then $n = ab$ for integers $a, b \ge 2$, then take $$(a_1, a_2,\dots,a_{n-1}, a_n) = (a, a, \dots , a, 0)$$
 If $n$ is prime. Say the statement does not hold. Then, construct a directed graph $G$ with vertices $1, 2,\dots,n$. For
each $a_i$, there exists $1 \le j \le n - 1$ such that
$a_i + a_{i+1} +\dots+ a{j-1}$
is divisible by $n$. 
Make directed edge from $i$ to $j$. Note that every vertex has out degree $1$. So $G$ is union of directed cycles.
When we total sum the terms from each vertex, we get it to be divisible by $n$. Each $a_i$ would  appear equal amount of times. (that would be less than $n-1$). But the total sum is divisible by $n$. So $n|a_1+\dots+a_n$. Contradiction.
</div>
<div class='remark'>
The idea for constructing a graph was very new and something to keep in mind!
</div>
<div class='problem'> [ISL 2012 A5]
 An integer $n \geq 3$ is given. We call an $n$-tuple of real numbers $(x_1, x_2, \dots, x_n)$ Shiny if for each permutation $y_1, y_2, \dots, y_n$ of these numbers, we have
$$\sum \limits_{i=1}^{n-1} y_i y_{i+1} = y_1y_2 + y_2y_3 + y_3y_4 + \cdots + y_{n-1}y_n \geq -1.$$Find the largest constant $K = K(n)$ such that
$$\sum \limits_{1 \leq i \le j-1 \leq n} x_i x_j \geq K$$holds for every Shiny $n$-tuple $(x_1, x_2, \dots, x_n)$.
</div>
<div class='proof'>
 Construct a graph $G=K_n$ on the $x_i$. Label each edge $x_i \sim x_j$ with a weight $x_ix_j$. We have to show that if sum of the weights in any Hamiltonian path is at least $-1$, then the sum of all weights is at least $\tfrac{1-n}{2}$.
 Take $x_1 = x_2 = \dots = x_{n-1} = \varepsilon, x_n = -\frac{1}{2\varepsilon}$.
Then we get that\[ \sum_{1 \le i \le  j-1 \le n} x_ix_j = \varepsilon^2 \cdot \frac{(n-1)(n-2)}{2} - \frac{n-1}{2} \]which approaches $-\frac{n-1}{2}$ as $\varepsilon$ approaches $0$.

For odd $n$: Decompose $K_n$ into $\frac{n-1}{2}$ hamiltonian cycles. Note that the weights of each path is at least $-1$.

For even $n$: WLOG $x_1\le x_2\dots \le x_k\le 0\le x_{k+1}\dots \le x_n$. Note that $$2(x_1x_2+\dots x_{n-1}x_n)\ge (x_2x_3\dots x_{n-1}x_n)+x_kx_{k-1}\ge (x_2x_3\dots x_{n-1}x_n)+x_{n}x_1\ge -1$$$$\implies x_1x_2+\dots x_{n-1}x_n=-1/2.$$ Now, just choose a suitable permutation.
</div>
