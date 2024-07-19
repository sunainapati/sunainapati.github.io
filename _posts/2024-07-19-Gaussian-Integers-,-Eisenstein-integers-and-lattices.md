---
layout: post
_title: Gaussian Integers, Eisenstein Integers and lattices
tags: ["number-theory","Abstract-algebra"]
---

<div class='theorem'>
$\Bbb{Z}[i]$ is an euclidean domain and PID.
</div>
<div class='proof'>
 We define the norm function as $$ N:\Bbb{Z}[i]\rightarrow \Bbb{Z}^{\ge 0}, N(z)=|z|^2.$$
 Note that $$N(z)=0\iff z=0.$$
 Now, to show the existence of $q,r$ such that $z=qw+r,N(r)\le N(w)-1$
 Let $\frac{z}{w}=t+is$ where $t,s\in \Bbb{Q}$ after rationalising the denominator. 
 Choose integers such that $$|t-a|\le \frac{1}{2}, |s-b|\le \frac{1}{2}.$$
 So $$z=w(t+is)=w(a+ib)+w((t-a)+i(s-b)= wq+r.$$ To show the norm condition is satisfied, note $$N(r)=N(w)N((t-a)+i(s-b))=N(w)(1/4+1/4)=N(w)/2\le N(w)-1.$$
</div>
<div class='remark'>
 Note that it is a PID as every euclidean domain is a PID. 
</div>
<div class='theorem'>
 Prove that $\mathbb{Z}[\zeta_3]$ is PID and Euclidean domain.
</div>
<div class='proof'>
 Consider the lattice $\mathbb{Z}[\zeta_3]$ in $\mathbb{C}$ ($\zeta_3 = \frac{-1+\sqrt{-3}}{2}$). So the lattice is all the points in $\Bbb{Z}[\zeta_3]$.Given $a,b\in\mathbb{Z}[\zeta_3]$, $a\neq 0$. Consider the points in the lattice which are multiples of $a$, and use them to tile the complex plane. Then locate $b$, and the closest corner of one of the squares to $b$, $qa$. Then let $r=b-qa$.
 Note that the tillinig passes through $a$ and $0$. One such square is $0,a,a(\zeta_3), a(\zeta_3)+a$ ( by vector addition).
 Note that $$N(r)\le a\sqrt{2}/2\text{ less than }N(a).$$
 Hence a Euclidean domain and a PID.
</div>
