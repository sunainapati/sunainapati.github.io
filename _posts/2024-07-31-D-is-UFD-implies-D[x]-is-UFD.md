---
layout: post
_title: D is UFD implies D[x] is UFD
tags : Number-theory Abstract-algebra 
---

Hi, today we will discuss something which has really intrigued me for a while! It is to show that if $D$ is a UFD then so is $D[x]$. A very common example is $\Bbb{Z}$ is UFD and so is $\Bbb{Z}[x]$. However, converse may not be true. For example, we know that $\Bbb{Q}[x]$. But $\Bbb{Q}$ is not. 
Also here $Q(D)$ represents the field of fractions of $D$. It is the smallest field which contains a copy of $D$.

# Contents
{:.no_toc}

* A markdown unordered list which will be replaced with the ToC, excluding the "Contents header" from above
{:toc}

# Valuation

Say $D$ is a UFD.

We will fix a subset, $\mathscr{P}_D$  of irreducible elements of $D$ with the following properties:
- Every element of $\mathscr{P}_D$ is irreducible
- For every irreducible element of $D$, there is a unique element $\overline{p}\in \mathscr{P}_D$ such that $p=u\overline{p},u\in D^{\times}$.

<div class="claim">
There is a bijection between $\mathscr{P}_D$ and set of principal prime ideals.
</div>
<div class="proof">
We know that $p$ is irreducible $\iff$ $p$ is primes $\iff$ $\langle p\rangle$ is a prime ideal. And note that $\langle p\rangle=\langle \overline{p}\rangle$.
</div>

So once we have fixed $\mathscr{P}_D$, our "expansion" of the number (or we can say "factorization") is now unique. We get that there is unique $u_a\in D^{\times}$ and $n_p\ge 0\in \Bbb{Z}$ such that $$a=u_a\prod_{p\in\mathscr{P}_D}p^{n_p}.$$

So we define $n_p$ as the $v_p(a)$ and $\sigma(a)=u(p)$. We also define $|a|=\sigma(a)^{-1}a=\prod_{p\in\mathscr{P}_D}p^{n_p}$. We call $v_p(a)$ $p$-valuation of $a$.

We can think about $\Bbb{Z}$ when working! For example, $\sigma(a)$ is just the sign of $a$, when we fix $\mathscr{P}_{\Bbb{Z}}$ as $\{p: p\text{ is positive prime}\}$.

Now, there are some obvious properties which are true in $\Bbb{Z}$ and are also true in any UFD.

<div class="theorem">
- \sigma(ab)=\sigma(a)\sigma(b)
- |ab|=|a||b|
- $v_p(ab)=v_p(a)+v_p(b)$ 
-$a|b\iff v_p(a)\le v_p(b)$
- $a=bu,u\in D^{\times}\iff v_p(a)=v_p(b)$
</div>
I am going to skip proof as it is very obvious. People who are interested and can't find proof can google it up. I am lazy :P

We can now work in $Q(D)$. 

# Existence and uniqueness of GCD in UFD

<div class="theorem">
Suppose $D$ is a UFD. Then for non zero elements $a_1,\dots,a_n$, there is $d\in D$ such that 
- $d|a_1,\dots,d|a_n$
- $d'|a_1,\dots,d'|a_n\implies d'|d$
If $d_1$ and $d_2$ satisfy this then $d_1=ud_2$ for $u\in D^{\times}$. 
</div>
That element is called **gcd**.

<div class="proof">
Suppose $a_1,\dots,a_n$ are non zero. We know that $b|a_1,\dots,b|a_n$, so $v_p(b)\le v_p(a_i)\forall p\in \mathscr{P}_D$. Let $$d=\prod_{p\in\mathscr{P}_D}p^{\min\{v_p(a_1),\dots,v_p(a_n)\}.$$ This is eesentially the same way we find gcd in $\Bbb{Z}$. 
Note that $b|a_1,\dots, b|a_n\iff b|d$. So existence done.
Say $d_1$ and $d_2$ both satisfy the above property. So $d_1|d_2,d_2|d_1$. So $d_2=ud_1$. Done.
</div>

# Primitive polynomial and content uniqueness

<div class="theorem">
Suppose $D$ is a UFD and $Q(D)$ is the field of fractions of $D$. Then for every non-zero polynomial $f\in Q(D)[x]$, there are unique $q\in Im(|.|)$ and primitive polynomial $\overline{f}\in D[x]$ such that $f(x)=q\overline{f}(x)$.
</div>
Not going to prove it as I myself have not understood it intuitively and also I have not understood the significance of $im|.|$. So will write proof when I am confident that it is correct.

# Gauss lemma

<div class="theorem">
Suppose $f,g\in D[x]$ are primitive. Then $fg$ is primitive.
</div>
<div class="proof">
Suppose $fg$ is not primitive. Then $\exists p\in \mathscr{P}_D$ such that $p|\alpha(fg)$. So all the coefficients $fg\in \langle p\rangle$. So $c_p(fg)=0$. As $D$ is UFD$\implies \langle p\rangle$ is a prime ideal. So $ D/\langle p\rangle$ is an Integral domain. So we work $ D/\langle p\rangle[x]$ which is also ID. As $c_p(f)c_p(g)=0\implies c_p(f)=0$ or $c_p(g)=0$, where $c_p$ is the residue map mod $p$.
</div>

<div class="theorem">
Suppose $D$ is a UFD. Then for every $f,g\in Q(D)[X]\\{0\}$ we have $\alpha(fg)=\alpha(f)\alpha(g)$. 
</div>
<div class="proof">
We know $f(x)=\alpha(f)\overline{f}(x)$ and $g(x)=\alpha(g)\overline{g}(x)$. So $fg=\alpha(f)\alpha(g)\overline{f}(x)\overline{g}(x)$. By gauss lemma, we get that $\overline{f}(x)\overline{g}(x)$ is a primitive polynomial. By comparing, we get that $\alpha(fg)=\alpha(f)\alpha(g)$.
</div>
<div class="remark">
So we also get 
  $$\overline{fg}(x)=\overline{f}(x)\overline{g}(x)$$
</div>



# Irreducible in $D[x]\iff$ irreducible in $Q(D)[x]$



Well, firstly by the previous post, we get that $Q(D)$ is a field and so $Q(D)[x]$ is PID and hence a UFD.
Clearly say if $p(x)$ is irreducible in $F[x]$ then it is clearly irreducible in $D$. So we just have to show that converse is true. 

<div class="theorem">
Suppose $p(x)\in D[x]$ with $p(x)=f(x)g(x)\in F[x]$ then there are $\overline{f}(x),\overline{g}(x)\in D[x]$ such that $p(x)= c\overline{f}(x)\overline{g}(x)$.
</div>
<div class+"proof">
Take $a,b\in D$ such that $af(x)\in D[x]$ and $bg(x)\in D[x]$. Then $af(x)=\overline{a}\overline{f}(x)$ and $bg(x)=\overline{b}\overline{g}(x)$ with $\overline{f}(x),\overline{g}(x)$ being primitive. Comparing contents, we get that $ab|\overline{a}\overline{b}$. So $\overline{a}\overline{b}=cab$. So $p(x)=c\overline{f}(x)\overline{g}(x)$.
</div>

# Main proof

<div class="proof">
Here let $F=Q(D)$.
Let $p(x)\in D[x]\subset F[x]$ Then $p(x)=f_1(x)\dots f_n(x)$ where $f_i\in F[x]$ are primitive and irreducible. Then we can factor in $D[x]$ by the above theorem. And then we know that they would be irreducible there too. So existence done.
For uniqueness, say $p(x)=a_1\dots a_nf_1(x)\dots f_n(x)=b_1\dots b_m g_1(x)\dots g_m(x)$. By $F[x]$ being a UFD, we get $m=n$ and $g_i=\frac{c_i}{d_i}f_i(x)$ after rearranging. By comparing contents and knowing they are primitive implies $c_i=d_iu_i,u_i\in D^{\times}$.
So $$a_1\dots a_nf_1(x)\dots f_n(x)c_1\dots c_n=b_1\dots b_nc_1\dots c_n u_1\dots u_n f_1(x)\dots f_n(x)$$
$$\implies a_1\dots a_n=b_1\dots b_n u_1\dots u_n$$
And done! 
</div>

So the uniqueness is proven too and we are done!
Phew! Huge thing done!
