---
layout: post
_title: Gaussian Integers is Euclidean Domain
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
