---
layout: post
_title: Chinese Remainder theorem
tags : Number-theory Abstract-algebra Olympiad-Number-theory
---

Hello, I have been thinking of proving CRT since a while. It makes sense to me intuitively on why it is true as essentially $$\Bbb{Z}/{mn\Bbb{Z}}\cong \Bbb{Z}/{m\Bbb{Z}}\times \Bbb{Z}/{n\Bbb{Z}}, \gcd(m,n)=1$$ so there is some isomorphism. However, let us prove it for ideals. Also, note that we can generalise the result to any number of ideals. 

Let $R$ be a ring and $I$ and $J$ be ideals in $R$ such that $I+J =R$. So $I,J$ are co-maximal ideals. 

<div class="theorem">
Show that for any $r$ and $s$ in $R$, the system of equations
\begin{align*}
  x & \equiv  r \pmod{I} \\ 
  x & \equiv  s \pmod{J}
\end{align*}
has a solution.  
</div>
<div class="proof">
We have $I+J=R$, so there exist $i \in I,j \in J$ such that $i+j=s-r$. Put $p=r+i=s-j$, and we get $p$ is a solution of the system since $p\in r+I$ and $p\in s+J$.
</div>

<div class="theorem">
Prove that any two solutions of the system are congruent modulo $I \cap J$. 
</div>
<div class="proof">
Say we get two different solutions $x$ and $x'$. Then 
\begin{align*}
 x &\equiv x' \pmod{I} \\
 x &\equiv x' \pmod{J} \, ,
\end{align*}
So $x - x'$ is in $I$ *and* $J$ 
  $$\implies x - x' \in I \cap J\implies x \equiv x' \pmod{I \cap J}.$$
</div>
<div class="theorem">
Let $I$ and $J$ be ideals in a ring $R$ such that $I + J = R$. Show
that there exists a ring isomorphism
$$ R/(I \cap J) \cong R/I \times R/J. $$
</div>
<div class="proof">
  Note that by first part, we get the surjectivity. Using the isomorphism theorem and considering the map,
  \begin{align*}
  \phi:  R &\rightarrow R/I \times R/J \\
         x &\mapsto (x + I, x + J) \, .
\end{align*}
Note that The kernel of $\phi$ is when $x \in I,J$. We get that the kernel of the map is $I\cap J$. So 
$$R/(I \cap J) \cong R/I \times R/J.$$
</div>

