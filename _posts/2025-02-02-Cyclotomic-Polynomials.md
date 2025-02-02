---
layout: post
_title: Cyclotomic Polynomials
tags : Number-theory
---
Just my notes on Cyclotomic polynomials. A pdf version is available [here](https://sunainapati.github.io/cyclotomic.pdf).

# Contents
{:.no_toc}

* A markdown unordered list which will be replaced with the ToC, excluding the "Contents header" from above
{:toc}

# Introduction
 A lot of references have been used:
- This [math StackExchange](https://math.stackexchange.com/a/532977/736863) answer
- [MIT lecture notes](https://ocw.mit.edu/courses/18-781-theory-of-numbers-spring-2012/7312c3e8e2dbb9af9a1677425fc3a0e7_MIT18_781S12_lec12.pdf)
- Brett Porter's Cyclotomic polynomials, Ramprasad Saptarishi's scribed Computational Number theory lecture 23 and 24 
- Evan Chen's modulo a prime.

# Cylcotomic Polynomials 
<div class='definition'>[primitive $n$-th roots of unity]
 For $n\geq 1$, the primitive $n$-th roots of unity are the $\omega\in\Bbb C$ such that $\omega^n=1$, and $\omega^k\neq1$ for $1\leq k$ < $n$.  
More explicitly, these are given by
$$e^{\frac{2\pi ik}{n}},1\leq k\leq n, (k,n)=1.$$
</div>

Note that there are precisely $\varphi(n)$ many primitive $n$-th roots of unity.

<div class='definition'>
 The $n$-th cyclotomic polynomial $\Phi_n$ is defined by

$$\Phi_n(X):=\prod_j(X-\omega_j),$$

where the product is taken over all primitive $n$-th roots of unity $\omega_j$.
</div>

Note that the $n$-th roots of unity are precisely the union of the primitive $d$-th root of unity for $d\mid n$, so

$$X^n-1=\prod_{d\mid n}\Phi_d(X).$$ So we also get that $$\sum_{d\mid n}\varphi(d)=n.$$

<div class='example'>
 Here are the first few cyclotomic polynomials:

 - $\Phi_1(x)=x-1$
 - $\Phi_2(x)=x+1$
 - $\Phi_3(x)=x^2+x+1$
 - $\Phi_4(x)=x^2+1$

 </div>
 Now, we shall prove some properties about it.
 
 <div class='theorem'>
  For $n\geq1$, $\Phi_n(X)$ has integer coefficients.
 </div>
<div class='proof'>
We induct. For $n=1$, we have $\Phi_1(x)=x-1\in\Bbb Z[x]$. Say $\Phi_k(x)\in\Bbb Z[x]$ for all $k$< $n$.
Note that $$x^n-1=\prod_{d\mid n}\Phi_d(x)=\Phi_n(x)\prod_{d\mid n, d\ne n}\Phi_d(x)=\Phi_n(x)p_n(x),$$ 
where $p_n(x)=\prod_{d\mid n, d\ne n}\Phi_d(x)$. Then $p_n\in\Bbb Z[X]$ by induction.
Now, we state a claim.

<div class='claim'> 
 If $$(x^n -1) =({\sum}^m_{i=1}{a_i{x^i}})({\sum}^l_{j=1}{b_j{x^i}}),$$ where ${\sum}^m_{i=1}{a_i{x^i}}\in{\bf{Z}[x]},$ then $b_j\in \Bbb{Q},\forall j$.
</div>
<div class='proof'>
Note that since $a_m\cdot b_l=1\implies b_l\in \Bbb{Q}$. Similarly we can show all the $b_j$ lie in $\Bbb{Q}$.
</div>
So, by the above claim, we get $\Phi_n(x)\in\Bbb{Q}[x]$. 
Let $\alpha $ be the smallest positive rational such that $\alpha\Phi_n(x)\in\Bbb{Z}[x].$ Note that $\alpha$ must be an integer.
Also, note that gcd of the coefficients of polynomial $\alpha \Phi_n(x)=\Phi'_n(x)$ will be $1$. 

<div class='definition'>[Primitive Polynomial]
Call an integer polynomial primitive if gcd of the coefficients is $1$.
</div>

<div class='lemma'>
 Let $p(x),q(x)$ be two primitive polynomials. Then $p(x)\cdot q(x)$ is also primitive. 
</div>
<div class='proof'>
Let $p(x)q(x)=c_lx^l+\dots+ c_0$. Let $p(x)=b_mx^m+\dots +b_0, q(x)=a_nx^n=\dots+a_0$. Suppose $\gcd(c_l,\dots,c_0)>1$. Then $\exists$ prime $p$ which divides all the $c_i$. Since $p(x)$ is not primitive, $\exists b_j$ such that $p\nmid b_j'$. So ther must exist a minimal $b_j$ such that $p\nmid b_j$. Then $p|b_0,b_1,\dots, b_{j-1}$. 
Consider $c_j$. Since $$p|c_j\implies p|b_0a_j+b_1a_{j-1}+\dots b_ja_0\implies p|b_ja_0\implies p|a_0.$$ Similarly consider $c_{j+1}$. Since $$p|c_{j+1}\implies p|b_0a_{j+1}+\dots+b_{j}a_1+b_{j+1}a_0\implies p|a_1.$$ Continuing this process, we get that $p$ divides all the coefficients of $q(x)$, contradicting that it is primitive. 
</div>
Note that $\Phi'_n(x)$ and $p_n(x)$ are primitive. But note that $$\Phi'_n(x)\cdot p_n(x)=\alpha(x^n-1).$$ By above lemma, we should have $\alpha(x^n-1)$  to be primitive. Hence $|\alpha|$ is $1$. And so $\Phi_n(x)\in \Bbb{Z}[x]$.
</div>

Note that these polynomials are also irreducibles.
<div class='lemma'>
 Let $p$ be a prime and $n\geq1$. Then

$$\Phi_{pn}(X)=\begin{cases}\Phi_n(X^p)&p\mid n\\\frac{\Phi_n(X^p)}{\Phi_n(X)}&p\nmid n.\end{cases}$$
</div>

<div class='proof'>
 If $p\mid n$, note that the $p$-th roots of the primitive $n$-th roots of unity are the primitive $pn$-th roots of unity 
If $p\nmid n$, note that the $p$-th roots of the primitive $n$-th roots of unity are  the union of the primitive $n$-th and $pn$-th roots of unity.
</div>
<div class='lemma'>
 Let $n\geq3$ and $x\in(1,\infty)$. Then $$(x-1)^{\varphi(n)}<\Phi_n(x)< (x+1)^{\varphi(n)}.$$
</div>
<div class='proof'>
 For any primitive $n$-th root of unity $\omega$, we have $\lvert\omega\rvert=1$, so by triangle inequality, we get

$$x-1\leq\lvert x-\omega\rvert\leq x+1.$$ Hence taking products over all $\omega$ gives

$$(x-1)^{\varphi(n)}<\lvert\Phi_n(x)\rvert< (x+1)^{\varphi(n)}.$$

Note that $\Phi_n(x)>0$ for $x>1$. So done.
</div>


# Cyclotomic Polynomials for two variables 

Now we will see why we are dealing with cyclotomic polynomials. 
<div class='definition'>
Define
$$\Phi_n(a,b):=b^{\varphi(n)}\Phi_n\left(\frac ab\right).$$
</div>
Note that $\Phi_n(a,b)$ is an integer. 
Moreover, 
$$\begin{aligned}
\prod_{d\mid n}\Phi_n(a,b)&=\prod_{d\mid n}b^{\varphi(d)}\Phi_d\left(\frac ab\right)\\
&=\prod_{d\mid n}b^{\varphi(d)}\cdot \prod_{d\mid n}\Phi_d\left(\frac ab\right)\\
&=b^n\left[\left(\frac ab\right)^n-1\right]\\
&=a^n-b^n.
\end{aligned}$$
Similarly to previous sections, the following two propositions follow.

<div class='lemma'>
  Let $p$ be a prime and $n\geq1$. Then

$$\Phi_{pn}(a,b)=\begin{cases}\Phi_n(a^p,b^p)&p\mid n\\\frac{\Phi_n(a^p,b^p)}{\Phi_n(a,b)}&p\nmid n.\end{cases}$$
</div>
<div class='lemma'>
 Let $n\geq3$. Then

$$(a-b)^{\varphi(n)}<\Phi_n(a,b)< (a+b)^{\varphi(n)}.$$
</div>

# Orders and Cyclotomic Polynomials
Let $p\geq3$ be a prime such that $p\nmid a,b$. Let $n\geq1$, and let $k\geq1$ be minimal such that $p\mid a^k-b^k$. Then note that $k$ is order of $a/b$ modulo $p$. So $k|p-1$.

Moreover, note that $\Phi_n(a,b)|a^n-b^n$. 
<div class='theorem'>
 If $p$ is a prime and $\Phi(a)\equiv 0\pmod p\implies $ $\text{ord}_p(a)=n\implies p\equiv 1\pmod n$ or $p|n$.
</div>
<div class='proof'>
 Note that $$\Phi_n(X)|x^n-1\implies \Phi_n(a)|a^n-1\implies p|a^n-1\implies \text{ord}_p(a)|n.$$ If $\text{ord}_p(a)=n$ then the first case holds. 
 If $\text{ord}_p(a)<n$ then $\exists k<n$ such that $p|x^k-1$ and $\Phi_k(a)=1$. So $x^n-1$ has a root of multiplicity of atleast $2$. So $$(nx^{n-1},x^{n}-1)\ne 1\text{  in }\Bbb{F}_p\implies p|n.$$
</div>

# Any subgroup of a mulitiplicative group of a field is cyclic

<div class='lemma'>
 Let $G$ a finite group with $n$ elements. If for every $d \mid n$,  $\# \{x \in G \mid x^d = 1 \} \leq d$, then $G$ is cyclic.
</div>
<div class='proof'>
 Fix $d \mid n$ and consider the set $G_d$ made up of elements of $G$ with order $d$. Suppose that $G_d \neq \varnothing$, so there exists $y \in G_d$; it is clear that $\langle y \rangle \subseteq \{ x \in G \mid x^d = 1 \}$. But the subgroup $\langle y \rangle$ has cardinality $d$, so from the hypothesis we have that $\langle y \rangle = \{ x \in G \mid x^d = 1 \}$. Therefore $G_d$ is the set of generators of the cyclic group $\langle y \rangle$ of order $d$, so $\# G_d  = \phi(d)$.

We have proved that $G_d$ is empty or has cardinality $\phi(d)$, for every $d \mid n$. So we have:

\begin{align}
n &= \# G\\
& = \sum_{d \mid n} \# G_d \\
&\leq \sum_{d \mid n} \phi(d) \\
&= n.
\end{align}

Therefore $\# G_d = \phi(d)$ for every $d \vert n$. In particular $G_n \neq \varnothing$. This proves that $G$ is cyclic.
</div>
If $G$ is a finite subgroup of the multiplicative group of a field, then $G$ satisfies the hypothesis because the polynomial $x^d - 1$ has $d$ roots at most.

# Roots of unity on Finite fields 
<div class='theorem'>
 Let $K^{(n)}$ be splitting field of $x^n-1$. The set of all the roots be $E^{(n)}$. $K$ be field of char $p$. Then:

-  if $p\nmid n$ then $E^{(n)}$ is cyclic group of order $n$.
-  if $p\mid n\implies n=p^em,p\nmid m$ then $K^{(n)}=K^{(m)}, E^{(n)}=E^{(m)}$ and root of $x^n-1$ are $m$ elements each occuring with muliplicity $p^e$.
</div>

<div class='proof'>
 The second part follows because $$x^n-1=x^{mp^e}-1=(x^m-1)^{p^e}$$ by frobinious map. 
 The first pat is true because of the following: 
 Note that $x^n-1$ and $nx^n$ have common factor $1$. So no repeating root. The set of roots form a multiplicative group as if $\alpha,\beta \in E^{(n)}$ then $$(\alpha \beta^{-1})^n=\alpha^n\beta^{-n}=1\implies \alpha\beta^{-1}\in E^{(n)}.$$
 And any subgroup of a mulitiplicative group of a field is cyclic. 
</div>


# Cyclotomic polynomial on finite fields 

<div class='theorem'>
 Let $K=\Bbb{F}_p$ and $(p,n)=1,d=\text{ord}_n(p)$, $p$ is prime.
 Then: 

-  $K^{(n)}$ is the spliting field of any irreducible factor of $\Phi_n(x)$
-  $[K^{(n)}:K]=d$
</div> 

<div class='proof'>
 Let $\zeta$ be one primitive root of $\Phi_n(x)$. Note that $$\zeta\in \Bbb{F}_{p^k}\iff \zeta^{p^k}=\zeta~~(\text{as all element of the field satisfy}~~x^{p^k}-x=0)$$$$\iff \zeta^{p^k-1}=1\iff n|p^k-1\iff p^k\equiv 1\mod n.$$
 Note that since $d=\text{ord}_n(p)\implies \zeta\in \Bbb{F}_{p^d} $ but no proper subfield of $ \Bbb{F}_{p^d}$. So the minimal polynomial of $\zeta$ has degree $d$. Same for other primitive roots. So the spliting field $K^{(n)}=\Bbb{F}_{p^d}$ and $[K^{(n)}:K]=d$. 
</div>




Let $\zeta$ be a primitive- $n$ th root of unity. Note that $\zeta\in \Bbb{F}_p$ when $r=p-1$ as all the element of $\Bbb{F}_p$ are roots of $x^p-x$, hence all non zero elements are roots of $x^{p-1}-1$. Let $M(x)$ be the minimal polynomial of $\zeta$. 
We claim the following: 
<div class='theorem'>
 $$\text{deg}(M(x))=\text{ord}_r(p).$$
</div> 
<div class='proof'>
 Let $\text{deg}(M(x))=d$. Let the polynomial be $a_0+a_1x+\dots +a_dx^d$. Note that $$M(\zeta)=0\implies 0=(M(\zeta))^p\implies (a_0+a_1\zeta+\dots +a_d{\zeta}^d)^p=a_0^p+a_1^p{\zeta}^p+\dots +a_d^p{\zeta}^{pd}=a_0+a_1\zeta+a_d{\zeta}^d=0.$$
 $$M(\zeta)=0\implies M({\zeta}^p)=0.$$
 Similarly, we get ${\zeta}^{p^2},\dots, {\zeta}^{p^{d-1}}$ as the roots. 
 So the minimal polynomial has roots precisely;  $\zeta, {\zeta}^p,{\zeta}^{p^2},\dots, {\zeta}^{p^{d-1}}$ as it is degree $d$ polynomial. So note that ${\zeta}^{p^{d}}=\zeta^{p}$. All elements of $\Bbb{F}_{p^d}$ satisfy the equation $x^{p^d} - x = 0$. ($\Bbb{F}_{p^d}$ is the splitting field of this polynomial.) Thus, in particular, $\zeta^{p^d} = \zeta$. So $d=\text{ord}_r(p)$. 
</div>
<div class='remark'>
 This proof was in Professor Ramprasad's scribed notes. 
</div>

#  On primes dividing Cyclotomic polynomials
<div class='theorem'>
 Let $p\nmid n$ and $m|n$. Then $\Phi_n(x)$ and $x^m-1$ has no common root modulo $p$.
</div>
<div class='proof'>
 Note that $\Phi_n(x)|x^n-1$ and $x^m-1|x^n-1$. And $x^n-1$ has double root modulo $p$ iff $(x^n-1,nx^{n-1})>1$. But $p\nmid n$.
</div>
<div class='theorem'>
 Let $n$ be a positive integer. There are infinitely many primes congruent to $1 \mod n$.
</div>
<div class='proof'>
 Well, we prove it just like how we prove that there are infinitely many primes. 
 Say there are finite many primes say $p_1,p_2,\dots,p_k$. Then consider $\Phi_n(knp_1,p_2,\dots,p_k)$ for big enough $k$. Note the none $p_i|knp_1,p_2,\dots,p_k$. So a new prime $p$ divides it. However, note that by theorem $3.1$, we get that $p\equiv 1\mod n$.
</div>

# Irreducibility of Cyclotomic polynomials


Let $ \zeta$ be a primitive $ n^{th}$ root of unity and let $ f(z)$ be its minimal polynomial. Since $ \zeta$ is also a root of $ z^{n} - 1 = 0$, it follows that $ f(z)$ divides $ (z^{n} - 1)$ and by Gauss Lemma $ f(z)$ has integer coefficients. 
<div class='theorem'>
 If $ p$ is any prime which does not divide $ n$ then $ \zeta^{p}$ is a root of $ f(z) = 0$. 
</div>
<div class='proof'>
 Suppose not. Note that $ \Phi_{n}(\zeta^{p}) = 0$ and $\zeta$ is root of $\Phi_n(x)$. So $f(x)|\Phi_n(x)$. So $\Phi_n(x)=f(x)g(x)$. Note $g(x)\in \Bbb{Z}$.
 Therefore $ \zeta$ is a root of $ g(z^{p}) = 0$. Since $ f(z)$ is the minimal polynomial of $ \zeta$, it follows that $ f(z)$ divides $ g(z^{p})$ so that $ g(z^{p}) = f(z)h(z)$ where $ h(z)$ is monic with integer coefficients.Also since $ \Phi_{n}(z)$ is a factor of $ (z^n - 1)$ so that we have $ z^{n} - 1 = \Phi_{n}(z)d(z)$ where $ d(z)$  is monic and in $\Bbb{Z}[x]$.
 $$z^{n} - 1 = f(z)g(z)d(z)$$
$$g(z^{p}) = f(z)h(z)$$
Going $\mod p$, $$g(z^{p})=g(z)^p.$$ So any irreducible factor of $f(z)$ will divide $g(z)^p$ and hence $g(z)$. But $n$ is coprime to $p$. So no repeated roots. Contradiction.
</div>
$ f(z)$ is the minimal polynomial for $ \zeta^{p_{1}p_{2}\ldots p_{m}}$ where $ p_{1}, p_{2}, \ldots, p_{m}$ are any primes not dividing $ n$. It follows that $ \zeta^{k}$ where $ k$ is coprime to $ n$ is also a root of $ f(z)$. Thus all the primitive $ n^{th}$ roots of unity are roots of $ f(z) = 0$. Hence $ \Phi_{n}(z)= f(z)$.


# On coefficients of Cyclotomic polynomials 
<div class='theorem'>
 The coefficients of cyclotomic polynomials are palindromic for $n\ge 2$
</div>
<div class='proof'>
 This is by induction. For $n=2$ it is true. Note that $$\Phi_2\Big(\frac{1}{x}\Big)x^{\phi(2)}=\Phi_2(x).$$
 We will be showing that $$\forall n\ge 2, \Phi_n
 \Big(\frac{1}{x}\Big)x^{\phi(n)}=\Phi_n(x).$$
 However, $$\Phi_n\Big(\frac{1}{x}\Big)x^{\phi(n)}=\frac{(1/x)^n-1}{\prod_{d|n,d<n}\Phi_d(\frac{1}{x})}x^{\phi(n)}.$$ By induction hypothesis, $$=\frac{(1/x)^n-1}{\prod_{d|n,1<d<n}(\Phi_d(x))(1/x-1)x}x^{n}$$
 $$=\frac{1-x^n}{\prod_{d|n,1<d<n}(\Phi_d(x))(1/x-1)x}$$
  $$=\frac{1-x^n}{\prod_{d|n,1<d<n}(\Phi_d(x))(1-x)}$$
  $$=\Phi_n(x).$$
</div>

