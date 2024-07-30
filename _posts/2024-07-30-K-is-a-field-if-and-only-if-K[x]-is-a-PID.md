---
layout: post
_title: $K$ is a field if and only if $K[x]$ is a PID
tags : Number-theory Abstract-algebra 
---

Hi, today we will discuss something which a while ago when proving $\Bbb[Z]$ is UFD. I was confused why it was "obvious" that $\Bbb{Q}[x]$ is a UFD. 

# Contents
{:.no_toc}

* A markdown unordered list which will be replaced with the ToC, excluding the "Contents header" from above
{:toc}

# Proving it right away!

<div class="theorem">
$K$ is a field $\iff$ $K[x]$ is a PID
</div>
<div class="proof">
$\implies$ Let $K$ be a field. Let $I\unlhd K[x]$. Let $p(x)\in I$ be a polynomial with the smallest degree. 
<div class="claim">
If $g(x)\in I\implies p(x)|g(x)$.
</div>
<div class="proof">
If not then $g(x)=p(x)q(x)+r(x),\text{ deg }r(x)<\text{ deg }p(x)$. But that implies $r(x)\in I$. Not possible. 
</div>
$\impliedby$  Given $K[x]$ is a PID. We need to show $K$ is a field. Say we want to show that $u$ is a unit. Consider $\langle u,x \rangle$ which is ideal of $K[x]$. Note that by PID, $\exists f$ such that $\langle f\rangle=\langle u,x\rangle$. Now, clearly $f$ is constant by degree comparison. If $f$ is a unit then we are done. If not, then $\alpha(f)|\alpha(d)\forall d\in \langle f \rangle. But $\alpha(f)=1$.
</div>

# Some remarks

- I wanted to write a post on it to show the importance and the power this theorem holds. Essentially many of the lemmas I stated in the [blog post ED implies PID implies UFD](https://sunainapati.github.io/2024/07/29/ED-$-implies$-PID-$-implies$-UFD.html), such as,  if 
 $D$ is PID, then $p$ is is irreducible iff $\langle p\rangle $ is a maximal ideal can be used when $D$ is $\Bbb{Q}[x]$ or any other PID.

- Also, we will deal with the field of fractions soon, so a quick result!
<div class="theorem">
If $D$ is ID$\implies$ $Q(D)$ is a field $\implies Q(D)[x]$ is a PID $\implies Q(D)[x]$ is UFD.
</div>

And we are done!
