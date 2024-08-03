---
layout: post
_title: Some problems in modular arithmetic
tags : Olympiad-Number-theory
---
Hi, this post is essentially a collection of problems I asked the pre-egmotc kids to try! Most problems are from Evan's OTIS units or Aditya's Modern olympiad number theory book.


# Contents
{:.no_toc}

* A markdown unordered list which will be replaced with the ToC, excluding the "Contents header" from above
{:toc}



# Solution 1

<div class="problem">
 Let $p$ be an odd prime and $0\le k\le p-1$. Then show that $\binom{p-1}{k}\equiv (-1)^k\pmod p$.
</div>
<div class="proof">
We cite and prove the freshman's dream. 
<div class="claim">
 $$(x+y)^p\equiv x^p+y^p\pmod\equiv p$$ 
</div>
<div class="proof">
Note $$(x+y)^p\equiv \sum_{i=0}^p \binom{p}{i}x^iy^{p-i}\pmod p.$$ But note that $\binom{p}{i}=p\cdot \frac{(p-1)!}{i!(p-i)!}$. Clearly $\binom{p}{i}$ is an integer and there is no factor of $p$ dividing the deonominator for $1\le i\le p-1$. So we  get that $p|\binom{p}{i}$ for $1\le i\le p-1$.
</div>
So using the above lemma, we get that $x^p-1\equiv (x-1)^p\pmod p$ and say $p\nmid x-1$, then we get that $$x^{p-1}+\dots +1\equiv (x-1)^{p-1}\pmod p.$$
On comparing the coefficients,we are done.
</div>
<div class="remark">
 The main thing was to ``back track'' and know that the claim existed!
</div>


# USAMO 1998

<div class="problem">[USAMO 1998]
 Suppose that the set $\{1,2,\cdots, 1998\}$ has been partitioned into disjoint pairs $\{a_i,b_i\}$ ($1\leq i\leq 999$) so that for all $i$, $|a_i-b_i|$ equals $1$ or $6$. Prove that the sum\[ |a_1-b_1|+|a_2-b_2|+\cdots +|a_{999}-b_{999}|  \]ends in the digit $9$.
</div>
<div class="proof">
 Note that,
\[ \displaystyle\sum_{i=1}^{999} |a_i-b_i| = \displaystyle\sum_{i=1}^{999}  a_i - b_i \equiv \displaystyle\sum_{i=1}^{999}  a_i + b_i = \dfrac{1998\cdot 1999}{2} \equiv 1 \pmod{2}. \]
Also,
\[ \displaystyle\sum_{i=1}^{999}  a_i - b_i \equiv \displaystyle\sum_{i=1}^{999}  1 \equiv 999 \equiv 4 \pmod{5}. \]
So by CRT, we get that $\displaystyle\sum |a_i-b_i| \equiv 9 \pmod{10}$
</div>
<div class="remark">
 The trick here, was to use that $|a_i-b_i|\equiv a_i+b_i$ in $\pmod 2$. I have seen this trick being used various invariance problems! Let me cite one: Suppose the positive integer $n$ is odd. First Al writes the numbers $1, 2,\dots, 2n$ on the blackboard. Then he picks any two numbers $a, b$ erases them, and writes, instead, $|a - b|$. Prove that an odd number will remain at the end.  
 Also, using CRT is veryy common in modular arithmetic problems.
</div>


# USAMO 2011 P1

<div class="problem">[USAMO 2011 P1]
 Find, with proof, all positive integers $n$ for which $2^n + 12^n + 2011^n$ is a perfect square.
</div>
<div class="proof">
 We claim the answer is $n=1$, we get $$2^{1}+12^{1}+2011^{1} = 2025 =45^{2}.$$
If $n \geq 2$
$$2^{n}+12^{n}+2011^{n} \equiv 3^{n} \pmod{4}\implies n \equiv 0 \pmod 2$$ 
$$2^{n}+12^{n}+2011^{n} \equiv 2^{n}+1 \pmod{3}\implies n\equiv 1\pmod 2$$

</div>
<div class="remark">
 Here, you just have to try seeing $mod 4$ and $mod 3$ which is one of the first things one should try! Also remember $qrs$ are always $0,1$ $\pmod 4$. It is veryy interesting a fun! Turns out this $0,1$ $\pmod 4$ comes often in algebraic number theory! Will talk about it someday!
</div>


# ISL 2002 N1

<div class="problem">[ISL 2002 N1]
What is the smallest positive integer $t$ such that there exist integers $x_1,x_2,\ldots,x_t$ with\[x^3_1+x^3_2+\,\ldots\,+x^3_t=2002^{2002}\,?\]
</div>
<div class="proof">
Note that $x^3 \equiv 0, 1, -1 \pmod{9}$ for all integers $x$. So $2002^{2002} \equiv 4 \pmod{9}$, so we must have $t \le 4$.
But $t = 4$ is possible as $x_1 = x_2 = 2002^{667} \cdot 10, x_3 = x_4 = 2002^{667}$. 
</div>
<div class="remark">
 I do not know why but this problem always comes to my mind while seeing INMO 2023 P1!.
</div>


# IMO 2006 P4

<div class="problem">[IMO 2006 P4]
 Determine all pairs $(x, y)$ of integers such that\[1+2^{x}+2^{2x+1}= y^{2}.\]
</div>
<div class="proof">
Note that $y$ is odd. Clearly $(x,y)=(0,\pm 2)$ satisfies. Assume $x\ge 1$. Then by $\mod 8$, we get $x\ge 3.$ Note that $$2^x(2^{x+1}+1y^2-1=(y-1)(y+1).$$ Note that $$\gcd(y-1,y+1)=2.$$ We have two cases. 
Case 1: $v_2(y-1)=1,v_2(y+1)=x-1$ 
Proof: Then let $y=2^{x-1}\cdot k+1,~~k\text{ is odd}$ and $2^{x-1}=a$. We get $$2a(4a+1)=(ka+1)^2-1 \implies (8-k^2)a=2k-2.$$ We get that there is no such $k$. 
Case 2: $v_2(y+1)=1,v_2(y-1)=x-1$
Proof: So $y=k(2^{x-1})-1$ and $k$ is odd. Let $a=2^{x-1}$. We get $$2a(4a+1)=(ka-1)^2-1\implies 2+2k=(k^2-8)a.$$ Note that $k^2-8>2+2k$ for $k\ge 5$ and clearly $k>2$. So $k=3$ works. For $k=3$ we get $(x,y)=(4,\pm 23).$ So the answer is $\boxed{ (0,\pm 2),(4,\pm 23)}.$

</div>

# HMMT

<div class="problem">[HMMT]
 Find all pairs $(a,b)$ of positive integers such that $a^{2017}+b$ is a multiple of $ab$.
</div>
<div class="proof">(by Arjun Gupta on AoPS)
The answer is $(a,b) = (1,1),(2,2^{2017})$.
<div class="claim">
 $a^{2017} \mid b$.
</div> 
Proof: FTSOC choose a prime $p$ with $v_p(a^{2017}) > v_p(b)$. But $v_p(a) + v_p(b) \le v_p(a^{2017} + b) = v_p(b)$, so $v_p(a) \le 0$. But $v_p(a^{2017}) > 0$, contradiction. $\square$

Write $b = a^{2017} \cdot k$ with $k \in \mathbb Z_{>0}$. Then,
\begin{align*}
ab \mid a^{2017} + b \iff a^{2018} \cdot k \mid a^{2017} + k \cdot a^{2017} \iff ak \mid 1+k
\end{align*}So $k \mid 1+k$ forcing $k=1$. After that $a \mid 1+k = 2 ~ \iff ~ a \in \{1,2\}$, as desired. 
</div>

# ELMO 2017 P1

<div class="problem">[ELMO 2017 P1]
 Let $a_1,a_2,\dots, a_n$ be positive integers with product $P,$ where $n$ is an odd positive integer. Prove that$$\gcd(a_1^n+P,a_2^n+P,\dots, a_n^n+P)\le 2\gcd(a_1,\dots, a_n)^n.$$
</div>

<div class="proof">
 We can assume $\gcd(a_1,a_2,\dots, a_n)=1$, so it suffices to prove
$$d=\gcd(a_1^n+P,a_2^n+P,\dots a_n^n+P)\leq 2$$Let $p$ be a prime that divides that $\gcd$.
<div class="claim">
$p\nmid a_i$ and $p\nmid P$
</div>
<div class="proof">
If $p\mid a_i \Rightarrow p\mid P\Rightarrow p$ divides all $a_i$, which contradics $\gcd(a_1,a_2,\dots, a_n)=1$

</div>

We also have $d\mid a_i^n+P \hspace{0.2cm}\forall  i$, so $a_i^n\equiv -P\pmod d \Rightarrow$
$$P^n=(a_1a_2\cdots a_n)^n\equiv (-P)^n\equiv -P^n\pmod d$$so $2P^n\equiv 0\pmod d\Rightarrow d\mid 2$ as desired
</div>

# IMO 2009 P1

<div class="problem">[IMO 2009 P1]
 Let $ n$ be a positive integer and let $ a_1,a_2,a_3,\ldots,a_k$ $ ( k\ge 2)$ be distinct integers in the set $ { 1,2,\ldots,n}$ such that $ n$ divides $ a_i(a_{i + 1} - 1)$ for $ i = 1,2,\ldots,k - 1$. Prove that $ n$ does not divide $ a_k(a_1 - 1).$
</div>
<div class="proof">
Say $n|a_k(a_1 - 1)$. Then note that, the condition implies that $a_i \equiv a_ia_{i+1} \pmod n$ for all $i\mod k$. So we get that
\[
    a_1 \equiv a_1a_2 \equiv a_1a_2a_3 \equiv \dots \equiv a_1a_2\dots a_k \equiv a_2a_3 \dots a_k \equiv a_2a_3 \dots a_{k+1}\equiv \dots \equiv a_2 \pmod n,
\]But both $a_1,a_2\le n$ and distinct,not possible. So $n \nmid a_k(a_1-1)$
</div>


# APMO 2022 P1

<div class="problem">[APMO 2022 P1]
 Find all pairs $(a,b)$ of positive integers such that $a^3$ is multiple of $b^2$ and $b-1$ is multiple of $a-1$.
</div>
<div class="proof">(by bjump on aops)
Let $\tfrac{a^3}{b^2}=k$, if $b=1$ all $a \ge 2$ work. So assume $b\ge 2$ we have
\begin{align*}
a-1 \mid b-1 &\iff a-1 \mid (b-1)(b+1) \\
&\iff a-1 \mid (b-1)(b+1)-(a-1)(a^2+a+1) \\
& \iff a-1 \mid b^2-a^3 \\
&\iff a-1 \mid 1-\tfrac{a^3}{b^2} \\
&\iff a-1 \mid 1-k \\ 
&\iff a-1 \mid k-1
\end{align*}Therefore $a \le k,b$, and since $a^3=b^2k$, $a=b=k$, so the only possible ordered pairs $(a,b)$, are $(x,x)$, and $(x,1)$ for any integer $x \ge 2$
</div>

# Taiwan TST 2006

<div class="problem">[Taiwan TST 2006]
 Let $a$, $b$ be positive integers such that $b^n+n$ is a multiple of $a^n+n$ for all positive integers $n$. Prove that $a=b$.
</div>
<div class="proof">
We claim the following.
<div class="claim">
 $p \mid b-a$ for all primes $p$
</div>
<div class="proof">
</div>

Construct a value of $n$ such that
\begin{align*}
n &\equiv 1 \pmod{p-1} \\
n &\equiv -a \pmod p,
\end{align*}which must exist by CRT. So $a^n + n \equiv a-a \equiv 0 \pmod{p}$, so
\[0 \equiv b^n + n \equiv b-a \pmod{p}.
\]

Hence, $a=b$.
</div>
<div class="remark">
 This is just smart, but I have seen this been used a lot!
</div>



# USAMO 2018 P4

<div class="problem">[USAMO 2018 P4]
 Let $p$ be a prime, and let $a_1, \dots, a_p$ be integers. Show that there exists an integer $k$ such that the numbers
\[a_1 + k, a_2 + 2k, \dots, a_p + pk\]produce at least $\tfrac{1}{2} p$ distinct remainders upon division by $p$.
</div>
<div class="proof">(By shreyasharma on Aops, her solutions are pretty nice!)
It suffices to consider the expected value of distinct residues. Note that any two residues are distinct if and only if,
\begin{align*}
a_i + ik \equiv a_j + jk \pmod{p}\\
a_i - a_j \equiv k(j - i) \pmod{p}
\end{align*}Note that there is exactly one value of $k$ which satisfies this for any pair $(i, j)$. Thus any pair leave the same residue with probability $\frac{1}{p}$. Over all pairs, which there are $\binom{p}{2}$ of, we find that we have an expected
$\frac{1}{p} \cdot \binom{p}{2} = \frac{p-1}{2}$
pairs $(i, j)$ such that $a_i + ik \equiv a_j + jk \pmod{p}$. Then by probabilistic pigeonhole there is some $k$ such that we have at most $\frac{p-1}{2}$ such pairs. Thus we have some $k$ such that we have at least $p - \frac{p-1}{2} = \frac{p+1}{2}$ distinct residues.
</div>
<div class="remark">
 This problem just looked way more interesting to not put in the pset! Even though it is probably not an NT. Idkkkk 
</div>

# Some more problems!

<div class="problem">[USATST 2021 P1]
 Determine all integers $s \ge 4$ for which there exist positive integers $a$, $b$, $c$, $d$ such that $s = a+b+c+d$ and $s$ divides $abc+abd+acd+bcd$.
</div>
<div class="problem">[Some thing random]
 Find all pairs of positive integers $(a,b)$ such that\[ a^2b-1 \mid ab^3-1. \]
</div>




