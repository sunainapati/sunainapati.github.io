---
layout: post
_title: Zsigmondy’s Theorem and its Applications
tags : Number-theory Olympiad-Number-theory
---
I am very happy to share with everyone that my article on has appeared in [Mathematical Reflections - Issue 2 of 2025](https://www.awesomemath.org/mathematical-reflections/archives/). Here is the [pdf](https://www.awesomemath.org/wp-pdf-files/math-reflections/mr-2025-02/mr_2_2025_zsigmondys_theorem.pdf). 
Mathematical Reflections is a free online journal run by Awesomemath aimed primarily at high school students, undergraduates, and everyone interested in mathematics. Through articles and problems, they seek to expose readers to a variety of interesting topics that are fully accessible to the target audience. To the people who have heard the name Titu Andreescu ( or Titu's inequality), Awesomemath was founded by him. 

I am extremely grateful that Awesomemath and the mathematical reflections team gave me this opportunity :). I have made sure to make the article as self-contained as possible. The only prerequisite is comfort with modular arithmetic. I hope this article helps students interested in olympiad math and also in higher math.
# Contents
{:.no_toc}

* A markdown unordered list which will be replaced with the ToC, excluding the "Contents header" from above
{:toc}

# Introduction 
This is a more refined and self-contained version of [Yan Sheng's blog post](https://angyansheng.github.io/blog/an-elementary-proof-of-zsigmondys-theorem), [Bart Michels's paper](https://math.stackexchange.com/questions/660585/elementary-proof-of-zsigmondys-theorem/662196#662196) and [this AoPS post](https://artofproblemsolving.com/community/c1803h1043308_zsigmondys_theorem). 

Zsigmondy's Theorem states that if \( a > b \geq 1 \) are coprime integers and \( n \geq 2 \), then there exists a prime divisor of \( a^n - b^n \) that does not divide \( a^k - b^k \) for all \( 1 \leq k < n \), except when \( n = 2 \) and \( a + b \) is a power of \( 2 \) or when \( (a, b, n) = (2,1,6) \).

In this document, we will go through the proof of this theorem and some applications of this theorem in math olympiad problems.

# Zsigmondy's Theorem
<div class="theorem">
Zsigmondy's Theorem states that if \( a > b \geq 1 \) are coprime integers and \( n \geq 2 \), then there exists a prime divisor of \( a^n - b^n \) that does not divide \( a^k - b^k \) for all \( 1 \leq k < n \ ), except in the following cases:

 - \( n = 2 \) and \( a + b \) is a power of \( 2 \),
 -  \( (a, b, n) = (2,1,6) \).

</div>
<div class="example">
 Consider $(a,b,n)=(4,2,3)$. Then $4^3-2^3=56, 4^2-2^2=12, 4^1-2^1=2$. So one such nice prime would be $7$. 
</div>
<div class="definition">
 We call such a prime divisor, a primitive prime divisor of $a^n-b^n$.
</div>

We essentially want to find prime divisors of $a^n-b^n$ which LTE can handle to some extent.

# Lifting the Exponent Lemma 
We state and prove LTE first.
<div class="theorem">[LTE Lemma]
    Let \( p \) be a prime, and let \( x, y \in \mathbb{Z} \), with \( m \geq 1 \) such that \( x \equiv y \not\equiv 0 \pmod{p} \). Then:
    If \( p \geq 3 \), then  
        \[
        v_p(x^m - y^m) = v_p(x - y) + v_p(m).
        \]
    And If \( p = 2 \), then  
        \[
        v_2(x^m - y^m) =
        \begin{cases}  
        v_2(x^2 - y^2) + v_2(m), & \text{if } m \text{ is even,} \\  
        v_2(x - y), & \text{if } m \text{ is odd.}  
        \end{cases}
        \]
</div>
<div class="proof">  We use induction on $v_p(n).$  We show for $v_p(n)=0, v_p(n)=1$ and then use induction.

- We show it for $v_p(n)=0.$ That is show $v_p(x^n-y^n)=v_p(x-y)$, for $v_p(n)=0$.
To prove this, we will show,$$v_p\left(\frac{x^n-y^n}{x-y}\right)=v_p(x^{n-1}+yx^{n-2}+y^2x^{n-3}+\dots+y^{n-1})=0.$$
As $x\equiv y\pmod p$,
so,  $$x^{n-1}+yx^{n-2}+y^2x^{n-3}+\dots+y^{n-1}\equiv nx^{n-1}\pmod p. $$ And $p\nmid nx^{n-1}$
- We show it for $v_p(n)=1.$ That is show $v_p(x^n-y^n)=v_p(x-y)+1$
To show this is true, we will show, $$v_p\left(\frac{x^n-y^n}{x-y}\right)=v_p(x^{n-1}+yx^{n-2}+y^2x^{n-3}+\dots+y^{n-1})=1.$$
As $x\equiv y\pmod p\implies x=y+pk$,
so,  $$x^{n-1}+yx^{n-2}+y^2x^{n-3}+\dots+y^{n-1}\pmod {p^2} $$
$$\equiv (pk+y)^{n-1}+(pk+y)^{n-2}y+(pk+y)^{n-3}y^2+\dots+y^{n-1}\pmod {p^2}$$
$$\equiv (y^{n-1}+pk\cdot (n-1)y^{n-2})+(y^{n-1}+ypk\cdot (n-2)y^{n-3})+\dots+y^{n-1}\pmod {p^2}$$
$$\equiv n\cdot y^{n-1}+pky^{n-2}\frac{(n-1)(n)}{2} \pmod {p^2}$$
Since $(n,p^2)=p.$ Let $n'=n/p.$
$$\equiv n'\cdot y^{n-1}+ky^{n-2}\frac{(n-1)(n)}{2} \pmod {p}.$$ We have $p$ odd, so above is equivalent to $$\equiv n'\cdot y^{n-1}n'\pmod {p}$$
but $p \nmid n',y$. So done!
- Let's assume it's true for $v_p=0,1,\dots, j-1.$ Now, we will show it's true for $v_p(n)=j.$
Then let $n=p^j\cdot c.$
Then $$v_p(x^n-y^n)=v_p(x^{p^j\cdot c}-y^{p^j\cdot c})=v_p((x^{p})^{p^{j-1}\cdot c}-(y^{p})^{p^{j-1}\cdot c})$$
$$=v_p(x^p-y^p)+v_p(p^{j-1}\cdot c)=v_p(x-y)+1+j-1=v_p(x-y)+v_p(n)$$
</div> 

# The $n=2$ case 

<div class="theorem">
 If we have a tuple of the form $(a,b,n)=(a,b,2),(a,b)=1$ such that it has no primitive divisor then $a+b$ is perfect power of $2$.
</div>
<div class="proof">
If $a^2-b^2$ has no primitive divisor, then a prime $p$ which divides $a^2-b^2$ also divides $a-b$. Moreover, if $$p|a+b\implies p|a^2-b^2\implies p|a+b\implies p=2\implies a+b\text{ is a power of } 2.$$
</div>
So from now we assume that $n\geq3$.
\section{ Cyclotomic Polynomials}
<div class="definition">[Primitive \( n \)-th Roots of Unity]
    For \( n \geq 1 \), the primitive \( n \)-th roots of unity are the numbers \( \omega \in \mathbb{C} \) such that
    \[
    \omega^n = 1, \quad \text{and} \quad \omega^k \neq 1 \text{ for all } 1 \leq k < n.
    \]
    More explicitly, these are given by:
    \[
    \omega_k = e^{2\pi i k / n}, \quad \text{for } 1 \leq k \leq n \text{ and } \gcd(k, n) = 1.
    \]
</div>

Note that there are precisely $\varphi(n)$ many primitive $n$-th roots of unity.

<div class="definition">
 The $n$-th cyclotomic polynomial $\Phi_n$ is defined by

$$\Phi_n(X):=\prod_j(X-\omega_j),$$

where the product is taken over all primitive $n$-th roots of unity $\omega_j$.
</div>

Note that the $n$-th roots of unity are precisely the union of the primitive $d$-th root of unity for $d\mid n$, so

$$X^n-1=\prod_{d\mid n}\Phi_d(X).$$ Thus, we obtain that $$\sum_{d\mid n}\varphi(d)=n.$$

<div class="example">
 Here are the first few cyclotomic polynomials:

- $\Phi_1(x)=x-1$
- $\Phi_2(x)=x+1$
- $\Phi_3(x)=x^2+x+1$
- $\Phi_4(x)=x^2+1$

</div>
 Now, we shall prove some properties about it.
 
 <div class="theorem">
  For $n\geq1$, $\Phi_n(X)$ has integer coefficients.
 </div>
<div class="proof">
We induct. For $n=1$, we have $\Phi_1(x)=x-1\in\Bbb Z[x]$. Say $\Phi_k(x)\in\Bbb Z[x]$ for all $k\text{ less than }n $.
Note that $$x^n-1=\prod_{d\mid n}\Phi_d(x)=\Phi_n(x)\prod_{d\mid n, d\ne n}\Phi_d(x)=\Phi_n(x)p_n(x),$$ 
where $p_n(x)=\prod_{d\mid n, d\ne n}\Phi_d(x)$. Then $p_n\in\Bbb Z[X]$ by induction.
Now, we state a claim.
<div class="claim">
 If $$(x^n -1) =({\sum}^m_{i=1}{a_i{x^i}})({\sum}^l_{j=1}{b_j{x^i}}),$$ where ${\sum}^m_{i=1}{a_i{x^i}}\in{\bf{Z}[x]},$ then $b_j\in \Bbb{Q},\forall j$.
</div>
<div class="proof">
Note that since $a_m\cdot b_l=1\implies b_l\in \Bbb{Q}$. Similarly we can show all the $b_j$ lie in $\Bbb{Q}$.
</div>
So, by the above claim, we get $\Phi_n(x)\in\Bbb{Q}[x]$. 
Let $\alpha $ be the smallest positive rational such that $\alpha\Phi_n(x)\in\Bbb{Z}[x].$ Note that $\alpha$ must be an integer.
Also, note that gcd of the coefficients of polynomial $\alpha \Phi_n(x)=\Phi'_n(x)$ will be $1$. 
<div class="definition">[Primitive Polynomial]
Call an integer polynomial primitive if gcd of the coefficents is $1$.
</div>

<div class="lemma">
 Let $p(x),q(x)$ be two primitive polynomials. Then $p(x)\cdot q(x)$ is also primitive. 
</div>
<div class="proof">
Let $p(x)q(x)=c_lx^l+\dots+ c_0$. Let $p(x)=b_mx^m+\dots +b_0, q(x)=a_nx^n=\dots+a_0$. Suppose $\gcd(c_l,\dots,c_0)>1$. Then $\exists$ prime $p$ which divides all the $c_i$. Since $p(x)$ is not primitive, $\exists b_j$ such that $p\nmid b_j'$. So there must exist a minimal $b_j$ such that $p\nmid b_j$. Then $p|b_0,b_1,\dots, b_{j-1}$. 
Consider $c_j$. Since $$p|c_j\implies p|b_0a_j+b_1a_{j-1}+\dots b_ja_0\implies p|b_ja_0\implies p|a_0.$$ Similarly consider $c_{j+1}$. Since $$p|c_{j+1}\implies p|b_0a_{j+1}+\dots+b_{j}a_1+b_{j+1}a_0\implies p|a_1.$$ Continuing this process, we get that $p$ divides all the coefficients of $q(x)$, contradicting that it is primitive. 
</div>
Note that $\Phi'_n(x)$ and $p_n(x)$ are primitive. But note that $$\Phi'_n(x)\cdot p_n(x)=\alpha(x^n-1).$$ By above lemma, we should have $\alpha(x^n-1)$  to be primitive. Hence $|\alpha|$ is $1$. And so $\Phi_n(x)\in \Bbb{Z}[x]$.
</div>
 
 Note that these polynomials are also irreducibles.
 
<div class="proposition">
 Let $p$ be a prime and $n\geq1$. Then

$$\Phi_{pn}(X)=\begin{cases}\Phi_n(X^p)&p\mid n\\\frac{\Phi_n(X^p)}{\Phi_n(X)}&p\nmid n.\end{cases}$$
</div>

<div class="proof">
 If $p\mid n$, note that the $p$-th roots of the primitive $n$-th roots of unity are the primitive $pn$-th roots of unity 
If $p\nmid n$, note that the $p$-th roots of the primitive $n$-th roots of unity are  the union of the primitive $n$-th and $pn$-th roots of unity.
</div>
<div class="proposition">
 Let $n\geq3$ and $x\in(1,\infty)$. Then $$(x-1)^{\varphi(n)}<\Phi_n(x)< (x+1)^{\varphi(n)}.$$
</div>
<div class="proof">
 For any primitive $n$-th root of unity $\omega$, we have $\lvert\omega\rvert=1$, so by triangle inequality, we get

$$x-1\leq\lvert x-\omega\rvert\leq x+1.$$ Hence taking products over all $\omega$ gives
 
$$(x-1)^{\varphi(n)}<\lvert\Phi_n(x)\rvert< (x+1)^{\varphi(n)}.$$

Note that $\Phi_n(x)>0$ for $x>1$. So done.
</div>

# Cyclotomic Polynomials in Two Variables
Now we will see why we are dealing with cyclotomic polynomials. 
<div class="definition">
Define
$$\Phi_n(a,b):= b^{\varphi(n)}\Phi_n\left(\frac ab\right).$$
</div>
Note that $\Phi_n(a,b)$ is an integer. 
Moreover, 
$$\begin{aligned}
\prod_{d\mid n}\Phi_n(a,b)&=\prod_{d\mid n}b^{\varphi(d)}\Phi_d\left(\frac ab\right)\\
&=\prod_{d\mid n}b^{\varphi(d)}\cdot \prod_{d\mid n}\Phi_d\left(\frac ab\right)\\
&=b^n\left[\left(\frac ab\right)^n-1\right]\\
&=a^n-b^n.
\end{aligned}$$
Similarly to the previous sections, the following two propositions follow.

<div class="proposition">
  Let $p$ be a prime and $n\geq1$. Then

$$\Phi_{pn}(a,b)=\begin{cases}\Phi_n(a^p,b^p)&p\mid n\\\frac{\Phi_n(a^p,b^p)}{\Phi_n(a,b)}&p\nmid n.\end{cases}$$
</div>
<div class="proposition">
 Let $n\geq3$. Then

$$(a-b)^{\varphi(n)}<\Phi_n(a,b)< (a+b)^{\varphi(n)}.$$
</div>

#  Orders and Cyclotomic Polynomials
Let $p\geq3$ be a prime such that $p\nmid a,b$. Let $n\geq1$, and let $k\geq1$ be minimal such that $p\mid a^k-b^k$. Then note that $k$ is order of $a/b$ modulo $p$. Thus, $k|p-1$.

Moreover, note that $\Phi_n(a,b)|a^n-b^n$.  
\section{LTE on Cyclotomic Polynomials}
<div class="theorem">
 Let $p\geq3$ be a prime such that $p\nmid a,b$. Let $n\geq1$, and let $k\geq1$ be minimal such that $p\mid a^k-b^k$. Then

$$v_p(\Phi_n(a,b))=\begin{cases}v_p(a^k-b^k)&n=k\\1&n=p^\beta k,\,\beta\geq1\\0&\text{else}.\end{cases}$$
</div>
<div class="proof">
We begin with cases. 
    
**Case 1** : Note that if $k=n$ then $p\nmid a^n-b^n$. Hence
$$\begin{aligned}
v_p(a^k-b^k)&=v_p(a^n-b^n)=v_p(\Phi_n(a,b))+\sum_{d\mid n,\,d\neq n}v_p(\Phi_d(a,b))\\
&=v_p(\Phi_n(a,b))
\end{aligned}$$
Note that $$\sum_{d\mid n,\,d\neq n}v_p(\Phi_d(a,b))=0$$ because of the minimality of $k$ we assumes. If $v_p(\Phi_d(a,b))>0$ for some $d$, then $p|a^d-b^d$. Not possible.

So this proves the first statement.

**Case 2**: 
For $n=p^{\beta}k$ then we get

$$\begin{aligned}
v_p(a^k-b^k)+\beta&=v_p(a^{p^\beta k}-b^{p^\beta k})\\
&=\sum_{d\mid p^\beta k}v_p(\Phi_d(a,b))\\
&=\sum_{d\mid k}v_p(\Phi_d(a,b))+ v_p(\Phi_{pk}(a,b))+v_p(\Phi_{p^2k}(a,b))+\dots + v_p(\Phi_{p^{\beta}k}(a,b))\\
&=v_p(a^k-b^k)+ v_p(\Phi_{pk}(a,b))+v_p(\Phi_{p^2k}(a,b))+\dots + v_p(\Phi_{p^{\beta}k}(a,b))
\end{aligned}$$
$$\implies \beta=v_p(\Phi_{pk}(a,b))+v_p(\Phi_{p^2k}(a,b))+\dots + v_p(\Phi_{p^{\beta}k}(a,b)).$$
So, this implies $v_p(\Phi_{p^{j}k}(a,b))=1$.

**Case 3.1**:
 If $k\nmid n$, then $ p\nmid a^n-b^n$. So $p\nmid \Phi_n(a,b)\implies v_p(\Phi_n(a,b))=0$.

**Case 3.2**:  
If $k\mid n$, then $n=p^\beta mk$ for some $p\nmid m$ (so $\beta=v_p(\frac nk)$). We have dealt with the case $m=1$. If $m>1$ then $\Phi_n(a,b)$ is a factor of

$$\frac{\prod_{d\mid n}\Phi_d(a,b)}{\prod_{d\mid p^\beta k}\Phi_d(a,b)}=\frac{a^n-b^n}{a^{p^\beta k}-b^{p^\beta k}}.$$

But note that LTE gives $v_p(a^n-b^n)=v_p(a^{p^\beta k}-b^{p^\beta k})$, so $p$ does not divide $\Phi_n(a,b)$. So done.
</div>
<div class="theorem">[For $p=2$]
 Let $a,b$ be odd, and $n\geq1$. Then

$$v_2(\Phi_n(a,b))=\begin{cases}v_2(a-b)&n=1\\v_2(a+b)&n=2\\1&n=2^\beta,\,\beta\geq2\\0&\text{else}.\end{cases}$$
</div>
Left to the readers!

# Final Proof of Zsigmondy's Theorem 
Suppose that  $a^n-b^n$ has no primitive prime divisors. 

If $\Phi_n(a,b)>1$. Let $p$ be a prime factor of $\Phi_n(a,b)$. Then $p\mid a^n-b^n$, so there exists a minimal $1\leq k< n$ such that $p\mid a^k-b^k$. ( since we assumed that $a^n-b^n$ has no primitive prime divisors). 

**Case 1**: If $p\geq3$, since $k<n$ and $p|\Phi_n(a,b)$. We get that $v_p(\Phi_n(a,b))=1$ by the lemma 7.1. So $n$ is of the forms $p^{\beta}k$.We also know that $k|n$ and $k|p-1\implies k<p$. So note that $p$ is the largest prime factor of $n$. Suppose $q\ne p$ divides $\Phi_n(a,b)$. By similar reasoning, we get that $q$ is the largest prime factor of $n$. This is a contradiction, as we established $p$ as the largest prime factor.
Hence $\Phi_n(a,b)$ is $p$. 

**Case 2**: If $p=2$ then $n\geq3$ is a power of $2$, so $4\mid n$ implies ( as $n\ge3$). So 
$$\Phi_n(a,b)=a^{n/2}+b^{n/2}\equiv2\pmod 4.$$
So $v_p(\Phi_n(a,b))=1$.

So we get $$p\geq\Phi_n(a,b)\geq(a-b)^{\varphi(n)}\geq(a-b)^{p-1}.$$

If $a-b\geq2$, then $p=2$ and $n=2$ as we get $p\ge 2^{p-1}$ which fails for $p>2$.

If $a-b=1$, write $n=p^\beta k$. 

**Case 1:** If $\beta\geq2$ then

$$\begin{aligned}
p\geq\Phi_n(a,b)&=\Phi_{pk}(a^{p^{\beta-1}},b^{p^{\beta-1}})\\
&\geq(a^{p^{\beta-1}}-b^{p^{\beta-1}})^{\varphi(pk)}\\
&\geq a^p-b^p=(b+1)^p-b^p\\
&=pb^{p-1}+\cdots+1
\end{aligned}$$
Not possible. 

**Case 2**: $\beta=1$, so $n=pk$. Note $p\nmid k$. Infact $k<p$.

$$\begin{aligned}
p\geq\Phi_n(a,b)&=\frac{\Phi_k(a^p,b^p)}{\Phi_k(a,b)}\\
&\geq\left(\frac{a^p-b^p}{a+b}\right)^{\varphi(k)}\\
&\geq\frac{(a^p-b^p)^{\varphi(k)}}{a+b}\\
&\geq\frac{2^p-1}3.
\end{aligned}$$

Here, equality can only hold when $p=3$ and $b=1$ (so $a=2$). Also, since $k< p$, we have $k\in\{1,2\}$, so $n\in \{3,6\}$. But $2^3-1^3$ has $7$ as a primitive divisor. Note that $2^6-1^6$ has no primitive divisors. Hence we get the exception case.

This concludes the proof of Zsigmondy's Theorem.

# Sum Version of Zsigmondy's Theorem
The sum version follows from above
<div class="theorem">[Sum Version of Zsigmondy's Theorem]
    Let \( a, b \in \mathbb{N} \) such that \( \gcd(a, b) = 1 \) and \( n > 1 \). Then there exists a prime divisor of \( a^n + b^n \)
    that does not divide \( a^k + b^k \) for all \( k \in \{1, \dots, n-1\} \), except in the case \( 2^3 + 1 = 9 \).
</div>
<div class="proof">
We use zsigmondy on $2n$. We know there exist primitive prime divisor $p$ of $a^{2n}-b^{2n}$. Note $p|a^n+b^n$ as $p\nmid a^n-b^n$. Moreover, $p\nmid a^k+b^k$ $\forall k<n$ as then $p|a^{2k}-b^{2k}$.
</div>


# Some Olympiad problems 

<div class="problem">[ISL 2002 N3]
 Let $p_1,p_2,\ldots,p_n$ be distinct primes greater than $3$. Show that $2^{p_1p_2\cdots p_n}+1$ has at least $4^n$ divisors.
</div>

**Walkthrough:** 

- You would like to use zsigmondy here, but how?
- Take an arbitrary $d\mid p_1p_2\dots p_n$
- Can you now find distinct prime factors of $2^{p_1p_2\cdots p_n}+1$


<div class="proof">
Take an arbitrary $d\mid p_1p_2\dots p_n$. Note that $2^d+1\mid 2^{p_1 p_2... p_n}+1$. By Zsigmondy's, $2^d+1$ has a prime p s.t. $p\nmid2^{d_0}+1\forall d_0<d$, which implies for each $d$ ($2^n$ of them) there's at least a prime factor in $2^{p_1p_2...p_n}+1$. Since there are $2^n$ possible values for $d,$ by Zsigmondy's Theorem, it has at least $2^n$ distinct prime factors, which means it has at least $2^{2^n} \ge 4^n$ total factors. Note that the exceptional case $2^3+1$ does not occur because all primes $p_i$ are greater than $3.$
</div>
<div class="problem">[ISL 2000 N4]
 Find all triplets of positive integers $(a,m,n)$ such that $ a^m + 1 \mid (a + 1)^n$.
</div>
    
**Walkthrough** 
- It's just Zsigmondy

<div class="proof">
 From Zsigmondy's Theorem, $a^m+1$ has a prime factor that is not a factor of $a+1,$ unless $a=2$ and $m=3.$ Hence, we see that the given statement holds only if $(a,m,n)=(2,3,n)$ with $n\ge 2.$
</div>
<div class="problem">[IMO 2000 P5]
 Does there exist a positive integer $ n$ such that $ n$ has exactly 2000 prime divisors and $ n$ divides $ 2^n + 1$?
</div>

**Walkthrough:**

-  I will spoil it for you! Answer is yes.
-  Start with $9$ and then inductively find the next primes using Zsigmondy's theorem.


<div class="proof">
 We will induct. Take $n = 9$. Note $n \mid 2^n + 1$ and has exactly one prime factor.  We have found $n$ such that $n \mid 2^n + 1$. Take $p$ as a primitive prime divisor of $2^{2n} - 1$, by Zsigmondy. Note $p$ is relatively prime to $n$ as $n \mid 2^{\phi(n)} - 1$ yet $p \nmid 2^{\phi(n)} - 1$ from Zsigmondy. Also $p \mid 2^n + 1$ as we must have $p \nmid 2^n - 1$.
</div>
 
<div class="problem">[USATST 2012 P4]
 Find all positive integers $a,n\ge1$ such that $\forall$ primes $p$ dividing $a^n-1$, there exists a positive integer $m<n$ such that $p\mid a^m-1$.
</div>
     
**Walkthrough:**
- Check the edge cases of Zsigmondy!

One obvious solution is $(a,n)=(1,n)$. Assume $a>1$.
  We just have to check the exceptions of Zsigmondy which are $(a,n)=(2,6), (2^k-1,2)$. 
    
**Case 1**: $(2,6)$ does not work by brute force checking

**Case 2**: If $(a, n)=(2^k-1, 2)$. Then note $(2^k-1)^2-1=(2^k)(2^k-2)=(2^{k+1})(2^{k-1}-1)$. So the primes divide $2^{k-1}-1$ and $2$. So $m=1$ works as $(2^k-1)-1=2^k-2=2(2^{k-1}-1)$.




So this was it! I hope you liked the post :)


