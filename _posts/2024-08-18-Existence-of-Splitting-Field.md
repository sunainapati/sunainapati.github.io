---
layout: post
_title: Existence of Splitting Field
tags : Number-theory Abstract-algebra 
---

Hi, today we will discuss something which seems pretty obvious but I think fundamentally would be very useful :) 
# Contents
{:.no_toc}

* A markdown unordered list which will be replaced with the ToC, excluding the "Contents header" from above
{:toc}

# Irreducible and extension

<div class="lemma">
Suppose $F$ is field and $f(x)\in F[x]$ is an irreducible polynomial. Then there is a field extension $E$ of $F$ and $\alpha \in E$ such that $f(\alpha)=0$ and $E=F[\alpha]$.
</div>

Essentially, we will be taking $E=F[x]/\langle f \rangle$. We will show it is a field and that $F$ is a subfield of $E$ by showing that there is an injection from $F$ to $E$. We will then take $\alpha= x+\langle f\rangle\in E$. And show $f(\alpha)=f(x)+\langle f\rangle$. 

<div class="proof"> 
Let $E=F[x]/\langle f \rangle$. Since $F[x]$ is a PID, $f$ is irreducible $\implies \langle f \rangle $ is a maximal ideal $\implies F[x]/\langle f\rangle$ is a field. 
<div class="claim">
We show that $E$ is a field extension. 
</div>
<div class="proof">
  We send $g(x)\in F $ to $g(x)+\langle f \rangle\in E$. Note that this map is a homomorphism. But kernel of this map is ideal of $F$. Since $F$ is a field implies kernel is $0$ or $F$. Clearly it is not $F$. So, it is injective. 
</div>
<div class="claim">
$\lapha := x+ \langle f \rangle\in E$ is a zero of $f$.
</div>
<div class="proof">
Say $f(x)=a_nx^n+\dots+ a_0$. So in $E$, $$f(\alpha)=(a_n+\langle f \rangle)(x+ \langle f \rangle)^n+\dots+ a_0$$ $$=a_nx^n+\dots a_0 +\langle f\rangle=f(x)+\angle f\rangle =0+\langle f \rangle.$$
So $f(\alpha)=0$ in $E$.
</div>
<div class="remark">
Idk but to me, this part did not make sense initially. So I took an example. So I work with $\Bbb{R}[x]$ and $f(x)=x^2+1$. Then the map $x\mapsto x+\langle x^2+1 \rangle$ is same as saying $x\mapsto i$ because of the isomorphism between $$\Bbb{R}[x]/\langle x^2+1\rangle \cong \Bbb{R}[i].$$
</div>
 Now, to show $E=F[\alpha]$, note that any element of $E$, say $$\sum_{j=0}^m b_j x^j+ \langle f \rangle =  \sum_{j=0}^m (b_j + \langle f \rangle) (x + \langle f \rangle)^j \in F[\alpha]$$ and vice versa. 
</div>


# Existence of Splitting Field

<div class="theorem">
Suppose $F$ is a field and $f(x)\in F[x]$ is a non-constant polynomial. Then there is a field extension $E$ of $F$ and $\alpha_1,\dots, \alpha_n$ such that $$f(x)=a(x-\alpha_1)\dots (x_\alpha_n)$$ in $E$ and $E=F[\alpha_1,\dots,\alpha_n]$.
</div>

This $E$ is called a splitting field of $f(x)$ over $F$.

Also, here we essentially just use strong induction!

<div class="proof">
If $f$ is not irreducible in $F[x]$, then there are non constant $g(x), h(x)$ such that $f=gh$. Then using strong induction on $g(x), h(x)$ we get that $g(x)=a_1(x-\alpha_1)\dots (x-\alpha_m)$ and $E_1=F[\alpha_1,\dots,\alpha_m]$.
And $h(x)=a_2(x-\alpha_{m+1})\dots (x-\alpha_{n})$ and $E_2=F[\alpha_{m+1},\dots,\alpha_{n}]$. Then take $$E= [F[\alpha_1,\dots,\alpha_m]][\alpha_{m+1},\dots,\alpha_{n}]= F[\alpha_1,\dots,\alpha_m,\alpha_{m+1},\dots,\alpha_{n}].$$
  
If $f$ is irreducible in $F[x]$, then we use the above lemma and get that there is a field extension $E$ of $F$ and $\alpha \in E$ such that $f(\alpha)=0$ and $E=F[\alpha]$. Since $f(\alpha)=0$ in $E$ $\implies f(x)=(x-\alpha)g(x)$ in $E$.Now induct on $g$ and we are done!
</div>


