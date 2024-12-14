---
layout: post
_title: Euclid's Algorithm and Continued Fractions
tags : Algorithmic-Number-theory Number-theory
---


# Euclid's Algorithm and Continued Fractions
I am following Professor Swastik's Algorithmic Number Theory course notes offered at Rudgerts in 2014. 
We start with Lectures 1 and 2! 
 
## Greatest common divisor and recognizing rational numbers
<div class='definition'>
Given integrers $a,b$ &gt $0,\gcd(a,b):= \text{ largest } d>0 \text{ such that } d|a, d|b \text{ in } \Bbb{Z}.$ 
</div>
## Complexity of elementary arithmetic operations
Note: We know the computer processes and stores information in binary digits, so our input for any natural number $(a)_{10}$ will be in binary, so it will have $[\log_2(a)]$ many digits. 


- **Addition/ Subtraction** Naive algorithm ( simply add digit wise) for addition takes $O(\log a +\log b)$ time.
- **Multiplication** Naive algorithm ( simply multiplying the way we did in high school) will take $O(\log a+\log b)$.
- **Factoring** We essentially try finding the prime factors of the number. Say if the number is an $n$ bit number, then it would be atmost $2^n$ decimal number. The number of times we would have to perform the trial division is bounded above to the number of distinct primes dividing the square root of the number which is calculated by the $\pi$ function. We know that the $\pi(n)= \frac{n}{\log_e(n)}$. So it would take around $\frac{2^{n/2}}{n/2\log_e(2)}$. We also have to account for the division so $O(n^2\cdot \frac{2^{n/2}}{n/2\log_e(2)})$. In any case, this is exponential in terms of $n$ ( which is the number of digits in base $2$). 

### GCD
 We will give a polynomial time algorithm for computing the GCD for two positive integers. So if we have $a,b$ in decimal form, then the algorithm will have time complexity of $O(\text{ poly} (\log a,\log b))$.

### Euclid's GCD algorithm 
We begin with the following claim. 
<div class='claim'>
 Wlog $a>b$ then $\gcd(a,b)=\gcd(a-b,b)$
</div>
<div class='proof'>
 Note that $$\gcd(a,b)|a-b\implies \gcd(a,b)|\gcd(a-b,b).$$
 Similarly, we get $$\gcd(a-b,b)|a-b,\gcd(a-b,b)|b\implies \gcd(a-b,b)|a\implies \gcd(a-b,b)|\gcd(a,b).$$
</div>

So we get the following algorithm to compute $\gcd(a,b)$:

 - Find $q,r$ such that $a=qb+r,0\le r< b$
 - If $r=0$ then $b$ is the answer
 - Else compute $\gcd(b,r)$


### Runtime of the algorithm
We begin with the lemma. 
<div class='lemma'>
 If Euclidean Algorithm for $\gcd(a,b)$ takes $n$ steps, then $a\ge F_{n+1}$ and $b\ge F_{n}$
</div>
<div class='proof'>
 We prove by Induction. It is true for $n=1$. Say it is true for $n\le N$. Say $\gcd(a,b)$ takes $N+1$ steps. Then write $a=qb+r$. Then $\gcd(r,b)$ takes $N$ steps. So $$b\ge F_N,r\ge F_{N-1}\implies a\ge F_N+ F_{N-1}=F_{N+1}.$$
</div>
Note that $F_n=\theta((\frac{1+\sqrt{5}}{2})^n)$.
So, if $a,b\le n$ bits long, then $\gcd(a,b)$ will halt in $O(n)$ steps. ( it grows in log time). Accounting, for the division, we get $O(n^3)$. 

### Finding a rational approximation
<div class='problem'>
 Given $\alpha \in \Bbb{Q}$ as a ratio of $n$ bit integers, and $\Bbb{Q}\in \Bbb{N}$ find $a,q\in \Bbb{N}$ such that $|\alpha-\frac{a}{q}|= \min_{a,q;q\le Q}|\alpha-\frac{a}{q}|$
</div>

So, essentially, we are trying to find the closest integer fraction to $\alpha$ with a bounded denominator. 

Note that, we can simply bash and find a solution, but that will take  some large time ( not sure?)

### Continued Fractions
We consider the Euclid's GCD algorithm on $a>b$. Then:
$$a=bq_0+r_0$$

$$b=r_0q_1+r_1$$

$$r_0=r_1q_2+r_2$$

$$\vdots$$

$$r_{n-2}=r_{n-1}q_n+0$$

So $$\frac{a}{b}=q_0+\frac{r_0}{b}$$

$$\frac{b}{r_0}=q_1+\frac{r_1}{r_0}$$

$$\vdots$$

$$\frac{r_{n-2}}{r_{n-1}}=q_n$$

We can also represent it this way:


$$\frac{a}{b}= q_0+\cfrac{1}{q_1+\cfrac{1}{q_2+\cfrac{1}{q_3+\dots \frac{1}{q_n}}}}$$

Note this fraction will be continued since we are dealing with rational numbers. Infact, we can do it for any $\alpha\in \Bbb{R}^{+}$. 

Given $\alpha\in \Bbb{R}^{+}$, $\alpha=[\alpha]+\frac{1}{\alpha_1}, \alpha_2=[\alpha_2]+\alpha_3$ and so on.

Notation: $[\alpha_i]=a_i,[\alpha]=a_0$. 

We get that $$
\alpha=
a_0+\cfrac{1}{a_1+\cfrac{1}{a_2+\cfrac{1}{a_3+\dots \vphantom{\cfrac{1}{1}}}}}$$

Note that, the fraction terminates $\iff \alpha$ is rational. 

We define $\frac{p_0}{q_0}=a_0, \frac{p_1}{q_1}=a_0+\frac{1}{a_1},\dots $
<div class='claim'>
 $$p_nq_{n-1}-q_np_{n-1}=(-1)^{n+1}$$
</div>
<div class='proof'>
 We use matrices!
 Define  
 $$
  \left[ {\begin{array}{cc}
   p_1 & p_0 \\
   q_1 & q_0 \\
  \end{array} } \right]= \left[ {\begin{array}{cc}
   a_1a_0+1 & a_0 \\
   a_1 & 1 \\
  \end{array} } \right].
$$
Note that ( by induction simply) 
 $$\left[ {\begin{array}{cc}
   p_n & p_{n-1} \\
   q_n & q_{n-1} \\
  \end{array} } \right]
  \left[ {\begin{array}{cc}
   a_{n+1} & 1 \\
   1 & 0 \\
  \end{array} } \right]= 
  \left[ {\begin{array}{cc}
   p_{n+1} & p_{n} \\
   q_{n+1} & q_{n} \\
  \end{array} } \right]
  $$
And hence, the  $$
\det\left[ {\begin{array}{cc}
   p_n & p_{n-1} \\
   q_n & q_{n-1} \\
  \end{array} } \right]=(-1)^{n+1}.$$
</div>
So, this implies $p_n,p_{n-1}$ are relatively prime. Similarly $q_n,q_{n-1}$. 

$$\frac{a}{b}= a_0+\cfrac{1}{a_1+\cfrac{1}{a_2+\cfrac{1}{a_3+\dots \frac{1}{a_n+\frac{1}{z}}}}}$$
where $z$ is a variable. 

Note that the above would be of the form $$\frac{rz+s}{tz+u}, r,t,u,s,\in \Bbb{Z}.$$

<div class='claim'>
 $$\frac{rz+s}{tz+u}=\frac{p_nz+p_{n-1}}{q_nz+q_{n-1}}$$
</div>

<div class='proof'>
For this, we will induct on $n$. For $n=1$ it is true. Then consider $z'=\frac{a_nz+1}{z}$. Then by induction, we get $$\frac{p_{n-1}z'+p_{n-2}}{q_{n-1}z'+q_{n-2}}=\frac{p_{n-1}(a_nz+1)+p_{n-2}z}{q_{n-1}(a_nz+1)+q_{n-2}z}$$ $$=\frac{p_nz+p_{n-1}}{q_nz+q_{n-1}}.$$
</div>

How good a rational approximation can one get to a given real number $\alpha$? One trivial rational approximation to $\alpha$ is a number $\frac{a}{q}$ with $$\left| \alpha - \frac{a}{q}\right| \leq \frac{1}{2q},$$ (for any $q$ we can simply choose $a \in \Bbb{Z}$ at a distance at most $1/2$ from $q\alpha$)

<div class='theorem'>[Dirichlet's Theorem]
For every $\alpha \in \Bbb{R}$, either $\alpha$ is rational, or else there are infinitely many distinct rational numbers $\frac{a}{q}$ such that 
$$\left|\alpha - \frac{a}{q}\right| < \frac{1}{q^2}.$$
</div>
We prove the above theorem by proving the following stronger theorem:
<div class='theorem'>
For all $Q \in \Bbb{N}$, there is a rational number $\frac{a}{q}$ such that $q \leq Q$ and 
$$ \left| \alpha - \frac{a}{q}\right| < \frac{1}{qQ}.$$ 
</div>
<div class='proof'>

If we show that there is some $q$ with $q \alpha$ closer than $\frac{1}{Q}$ to some integer, then we can use that integer as our $a$ and be done. Consider $\{0\mod 1, \alpha\mod 1, \dots Q\alpha \mod 1\}$. This is an $Q +1$ element set lying in the interval $[0,1)$. There must be two in one of the $Q$ intervals $\left[\frac{i-1}{Q}, \frac{i}{Q}\right)$, $i \in \{1, \dots, Q\}$. Hence there exist $r,s$ such that $$0 \leq [s\alpha \pmod 1] - [r\alpha \pmod 1] = (s - r)\alpha \mod 1 < \frac{1}{Q},$$ viewed as an element of $[0,1)$. Then there is an integer, namely that integer directly below $(s-r)\alpha$, such that $\left|(s - r)\alpha - a\right| $ &lt $ \frac{1}{Q}$. Our $q$ is $s-r$.
</div>
We claim that theorem $2.2$ proves theorem $2.1$.
