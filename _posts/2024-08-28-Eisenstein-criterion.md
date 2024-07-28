---
layout: post
_title: Eisenstein Criterion for irreducibility
tags : Number-theory Abstract-algebra Olympiad-Number-theory
---

Hi, today we will discuss the Eisenstein Criterion for the irreducibility of polynomials in fields. This is something I have seen in olympaids a lot! 

# Contents
{:.no_toc}

* A markdown unordered list which will be replaced with the ToC, excluding the "Contents header" from above
{:toc}

# The theorem
We begin with a lemma. 
<div class="lemma">
 Suppose $F$ is a field and $g_1,g_2\in F[x]$ are two non constant polynomials such that $f_1(x)f_2(x)=cx^n$ for some $c\in F^{*}$ Then $f_1(0)=0,f_2(0)=0$. 
</div>
<div class="proof">
 Say $f_1(x)=b_rx^r+\dots b_1+b_0$, $f_2(x)=c_sx^s+\dots+c_1x+c_0$ where $b_i,c_j\in F$ and $b_r,c_s\in F^{*}$.
 By comparing coefficients, note that $c_0b_0=0\implies c_0=0\text{ or }b_0 =0$
 Then say $s'$ is the smallest such that $c_{s'}$ is nonzero. Similarly define $r'$.
 Note that coefficient of $x^{s'r'}=0$ if $r'<r$ or $s'<s$. Hence $s'=s,r'=r$.
</div>


<div class="theorem">
 Let $f(x)=a_nx^n+\dots+a_1x+a_0\in \Bbb{Z}[x]$ and $p$ be a prime. Suppose $p\nmid a_n,p\mid a_{n-1},\dots, p|a_0,p^2\nmid a_0$.Then $f(x)$ is irreducible in $\Bbb{Q}[x]$. 
</div>
<div class="proof">
 Suppose $\exists g_1,g_2\in \Bbb{Q}[x]$ such that $f(x)=g_1(x)g_2(x)$. Let $\overline{g_i}$  be the primitive prolynomial of $g_i$. So we know by gauss lemma, $$\alpha(f)=\alpha(g_1g_2)=\alpha(g_1)\alpha_2.$$
 Since $p\nmid a_n$ implies $p$ does not divide leading coefficient of $\overline{g_i}$.
 So we work in $\Bbb{Z}_p$ and use the above lemma. We get the both the polynomials $$\overline{g_i}(0)=0\implies p^2|\overline{g_1}(0)\overline{g_2}(0)\implies p^2|a_0.$$ Contradiction.
</div>

# Application of the theorem
<div class="example">
 Suppose $p$ is a prime. Then $f(x)=x^{p-1}+x^{p-2}+\dots+1$ is irreducible in $\Bbb{Q}[x]$.
</div>

<div class="proof">
 Note that $f(x)=\frac{x^p-1}{x-1}$. Let $g(y)=f(x+1)$. So $g(y)= y^{p-1}+\binom{p}{p-1}y^{p-2}+\dots+p$. Note by eisenstien, we get that $g(y)$ is irreducible in $\Bbb{Q}[x]$, and hence so is $f$.
</div>
 
