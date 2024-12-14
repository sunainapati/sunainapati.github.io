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
Given integrers $a,b>0,\gcd(a,b):= \text{ largest } d>0 \text{ such that } d|a, d|b \text{ in } \Bbb{Z}.$ 
</div>
## Complexity of elementary arithmetic operations
Note: We know the computer processes and stores information in binary digits, so our input for any natural number $(a)_{10}$ will be in binary, so it will have $[\log_2(a)]$ many digits. 


- **Addition/ Subtraction** Naive algorithm ( simply add digit wise) for addition takes $O(\log a +\log b)$ time.
- **Multiplication** Naive algorithm ( simply multiplying the way we did in highschool) will take $O(\log a+\log b)$.
- **Factoring** We essentially try finding the prime factors of the number. Say if the number is an $n$ bit number, then it would be atmost $2^n$ decimal number. The number of times we would have to perform the trial division is bounded above to the number of distinct primes dividing the squareroot of the number which is calculated by the $\pi$ function. We know that the $\pi(n)= \frac{n}{\log_e(n)}$. So it would take around $\frac{2^{n/2}}{n/2\log_e(2)}$. We also have to account for the division so $O(n^2\cdot \frac{2^{n/2}}{n/2\log_e(2)})$. In any case, this is exponential in terms of $n$ ( which is the number of digits in base $2$). 

### GCD
 We will give a polynomial time algorithm for computing the GCD for two positive integers. So if we have $a,b$ are in decimal form, then the algorithm will have time complexity of $O(\text{ poly} (\log a,\log b))$.

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
\begin{problem}
 Given $\alpha \in \Bbb{Q}$ as a ratio of $n$ bit integers, and $\Bbb{Q}\in \Bbb{N}$ find $a,q\in \Bbb{N}$ such that $|\alpha-\frac{a}{q}|= \min_{a,q;q\le Q}|\alpha-\frac{a}{q}|$
\end{problem}

So, essentially, we are trying to find the closest integer fraction to $\alpha$ with a bounded denominator. 

Note that, we can simply bash and find a solution, but that will take 
some large time ( not sure?)

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

\[
\mathrm{\frac{a}{b}}=
q_0+\cfrac{1}{q_1+\cfrac{1}{q_2+\cfrac{1}{q_3+\dots \frac{1}{q_n}}}}
\]

Note this fraction will be continued since we are dealing with rational numbers. Infact, we can do it for any $\alpha\in \Bbb{R}^{+}$. 

Given $\alpha\in \Bbb{R}^{+}$, $\alpha=[\alpha]+\frac{1}{\alpha_1}, \alpha_2=[\alpha_2]+\alpha_3$ and so on.

Notation: $[\alpha_i]=a_i,[\alpha]=a_0$. 

We get that \[
\alpha=
a_0+\cfrac{1}{a_1+\cfrac{1}{a_2+\cfrac{1}{a_3+\dots \vphantom{\cfrac{1}{1}}}}}
\]

Note that, the fraction terminates $\iff \alpha$ is rational. 

We define $\frac{p_0}{q_0}=a_0, \frac{p_1}{q_1}=a_0+\frac{1}{a_1},\dots $
<div class='claim'>
 $$p_nq_{n-1}-q_np_{n-1}=(-1)^{n+1}$$
</div>
<div class='proof'>
 We use matrices!
 Define  \[
  \left[ {\begin{array}{cc}
   p_1 & p_0 \\
   q_1 & q_0 \\
  \end{array} } \right]= \left[ {\begin{array}{cc}
   a_1a_0+1 & a_0 \\
   a_1 & 1 \\
  \end{array} } \right].
\]
Note that ( by induction simply) \[
\left[ {\begin{array}{cc}
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
  \]
And hence, the  \[
\det\left[ {\begin{array}{cc}
   p_n & p_{n-1} \\
   q_n & q_{n-1} \\
  \end{array} } \right]=(-1)^{n+1}.\]
</div>
So, this implies $p_n,p_{n-1}$ are relatively prime. Similarly $q_n,q_{n-1}$. 
\[
\mathrm{\frac{a}{b}}=
a_0+\cfrac{1}{a_1+\cfrac{1}{a_2+\cfrac{1}{a_3+\dots \frac{1}{a_n+\frac{1}{z}}}}}
\]
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

If we show that there is some $q$ with $q \alpha$ closer than $\frac{1}{Q}$ to some integer, then we can use that integer as our $a$ and be done. Consider $\{0\mod 1, \alpha\mod 1, \dots Q\alpha \mod 1\}$. This is an $Q +1$ element set lying in the interval $[0,1)$. There must be two in one of the $Q$ intervals $\left[\frac{i-1}{Q}, \frac{i}{Q}\right)$, $i \in \{1, \dots, Q\}$. Hence there exist $r,s$ such that $$0 \leq [s\alpha \pmod 1] - [r\alpha \pmod 1] = (s - r)\alpha \mod 1 < \frac{1}{Q},$$ viewed as an element of $[0,1)$. Then there is an integer, namely that integer directly below $(s-r)\alpha$, such that $\left|(s - r)\alpha - a\right| < \frac{1}{Q}$. Our $q$ is $s-r$.
</div>
We claim that theorem $2.2$ proves theorem $2.1$.
<div class='proof'>
 Take some $Q_1 \in \Bbb{N}$. So, we can find $\frac{a_1}{q_1}$ with 
$$ \left| \alpha - \frac{a_1}{q_1}\right| < \frac{1}{q_1Q_1} \leq \frac{1}{q_1^2}.$$ 
If $\frac{a_1}{q_1} = \alpha$, then $\alpha$ is rational, then we are done.
If not, then $ \left| \alpha - \frac{a_1}{q_1}\right| > 0$, then we can take a new $Q_2$ large enough such that $ \left| \alpha - \frac{a_1}{q_1}\right| > \frac{1}{Q_2}.$ Let $\frac{a_2}{q_2}$ be the pair guaranteed by Theorem for $Q_2$. Then 
$$ \left| \alpha - \frac{a_2}{q_2}\right| < \frac{1}{q_2Q_2} < \frac{\left| \alpha - \frac{a_1}{q_1}\right|}{q_2} \leq \left| \alpha - \frac{a_1}{q_1}\right|,$$ 
so $\frac{a_2}{q_2}$ is distinct from $\frac{a_1}{ q_1}$. Furthermore,
$$ \left| \alpha - \frac{a_2}{q_2}\right| < \frac{1}{q_2Q_2} \leq \frac{1}{q_2^2}.$$
</div>

## Approx

We are keeping in mind the convergents.
<div class='theorem'>Let $n$ be largest number such that $q_n \leq Q$, and let $t$ be the greatest integer such that $tq_n + q_{n-1} \leq Q$. Then either $\frac{p_n}{q_n}$ or $\frac{t p_n + p_{n-1}}{tq_n + q_{n-1}}$ is a solution to the rational approximation problem.
</div>
<div class='proof'>Let $L = \frac{t p_n + p_{n-1}}{tq_n + q_{n-1}}$. We will assume $n$ is even. The proof when $n$ is odd will be very similar. Because $n$ is even, $\frac{p_n}{q_n} \leq \alpha$ and $\frac{p_{n+1}}{q_{n+1}} \geq \alpha$. Note that if $s = a_{n+1}$, then $ \frac{s p_n + p_{n-1}}{sq_n + q_{n-1}} = \frac{p_{n+1}}{q_{n+1}}$. If $s = 0$, then $ \frac{s p_n + p_{n-1}}{sq_n + q_{n-1}} = \frac{p_{n-1}}{q_{n-1}}$. 
<div class='claim'>
 $s$ ranges from $0$ to $a_{n+1}$, $\frac{s p_n + p_{n-1}}{sq_n + q_{n-1}}$ ranges monotonically
</div>
<div class='proof'>
This is because $$\frac{d}{ds} \left(\frac{s p_n + p_{n-1}}{sq_n + q_{n-1}}\right) = \frac{p_n(sq_n+q_{n-1})-q_n(sp_n+p_{n-1})}{\left(sq_n + q_{n-1}\right)^2}=\frac{\det\left(\left[ \begin{array}{cc}
p_{n} & p_{n-1}   \\
q_{n} & q_{n-1}  \\
 \end{array} \right]\right)}{\left(sq_n + q_{n-1}\right)^2}$$
does not change sign.
</div>
  Hence, L must be between  $\frac{p_{n+1}}{q_{n+1}}$ and $\frac{p_{n-1}}{q_{n-1}}$, both of which are at least $\alpha$. Hence $L$ is at least $\alpha$. If $\frac{r}{s}$ is strictly closer to $\alpha$ than both $c_n$ and $L$, then $\frac{r}{s} \in I = (c_n, L)$. For contradiction, suppose $0 < s \leq Q$. Then 
 $$\left| \frac{r}{s} - \frac{p_n}{q_n}\right| \geq \frac{1}{s q_n},$$
 because $\frac{r}{s} \neq \frac{p_n}{q_n}$, and similarly 
 $$\left| \frac{r}{s} - L\right| \geq \frac{1}{s (t q_n + q_{n-1})}.$$
Observe that $|I| =\left|\frac{p_n}{q_n} - \frac{t p_n + p_{n-1}}{tq_n + q_{n-1}}\right| = \frac{1}{{q_n}(t q_n + q_{n-1})}$.
Then $$|I| = \frac{1}{{q_n}(t q_n + q_{n-1})} \geq \frac{1}{s (t q_n + q_{n-1})} + \frac{1}{s q_n} = \frac{1}{s}\left(\frac{1}{t q_{n} + q_{n-1}} + \frac{1}{q_n}\right) =\frac{1}{s}\left( \frac{t q_{n} + q_{n-1} + q_n}{q_n(t q_{n} + q_{n-1})}\right). $$
So $s \geq (t +1) q_n + q_{n-1} > Q$, a contradiction. </div>
<div class='remark'> So in  the last line only, we used that $(t+1)q_n+q_{n-1}>Q$.
</div>
We saw in the proof that if $n$ is even, $\alpha \in (c_n, L)$, and if $n$ is odd, $\alpha \in (L, c_n)$. Further, the interval has length exactly $\frac{1}{{q_n}(t q_n + q_{n-1})}$. Then $|c_n - \alpha| \leq \frac{1}{{q_n}(t q_n + q_{n-1})} \leq \frac{1}{q_n q_{n-1}}.$
 We know that one of $\frac{a}{q} = c_n$ and $\frac{a}{q} = L$ have $|\frac{a}{q} - \alpha| \leq \frac{1}{qQ}$. Then we must have that $|(c_n, L)| \geq |\frac{a}{q} - \alpha|$ Hence $|c_n - \alpha| \leq \frac{1}{{q_n}(t q_n + q_{n-1})} \leq \frac{1}{q_n q_{n-1}}$. 

As we noted before, $q_n$ increases monotonically until $n = N$. As $\frac{a}{b}$ is the best approximation with denominator at most $Q$ for any $Q \geq b$, we cannot have $q_n > b$ for any $n$. If so, then $q_{n+1} > b$ as well. Either $L$ or $\frac{p_{n+1}}{q_{n+1}}$ would at least as good an approximation as $\frac{a}{b}$ with denominator at most $q_{n+1}$. For any $t > 0$, $tq_{n+1}  + q_{n} > q_{n+1}$, so $t=0$. Then $L = \frac{p_{n}}{q_{n}}$. This is impossible, because $\frac{p_n}{q_n}$ and $\frac{p_{n+1}}{q_{n+1}}$ are reduced and therefore neither are equal to $\frac{a}{b}$. This also applies that $N$ exists for $\alpha$ if and only if $\alpha$ is rational., i.e. the continued fraction representation of $\alpha$ terminates iff $\alpha$ is rational.

## Running time
It will be of use to bound $p_n$ and $q_n$. We already know that $q_n \leq b$. From Remark, we know that $\left|p_n  -  q_n\frac{a}{b}\right| \leq \frac{1}{q_{n-1}}$. Hence $|p_n| \leq \left|\frac{q_n}{b}\right| \left|a\right| + \frac{1}{q_{n-1}} = O(a)$.

- We know that the $n$ from Theorem is $O(\log(Q))$ because the $q_n$ grow at least as fast as the $n^{th}$ entry of the Fibonacci sequence provided $n \leq N$.
- At each step in the computation of the continued fraction, we compute the floor of a rational number $\alpha_i = \frac{r_i}{s_i}$, which is simply the number of times the denominator of $\alpha_i$ goes into the numerator. This is division with remainder, which we know to take $O(\log(r_i)\log(s_i))$ operations.
- We know $\alpha_i = \frac{1}{\alpha_{i-1} - \lfloor\alpha_{i - 1}\rfloor}$, which has denominator the remainder of $r_{i - 1}$ under division by $s_{i - 1}$ (which is strictly smaller than $s_{i-1}$) and numerator $s_{i-1}$. As $\alpha_0 =\alpha = \frac{a}{b}$, we can conclude by induction that $r_i, s_i \leq \max(a, b)$ and so the number of operations per step is certainly at most $O((\log(a) + \log(b))^2)$.
- Finding $t$ can take at most $O(\log(Q)^2)$ steps, as we find it by division with remainder of $Q - q_{n-1}$ by $q_{n-1}$. $t$ is at most $a_{n+1}$, which is at most $q_{n+1} \leq b$. $p_n, p_{n-1} = O(a)$.
- Taken together, finding $L$ must take $O(poly(\log(a), \log(b), \log(Q)))$.
- Finding whether $L$ or $c_n$ is closer to $\alpha$ can also certainly take at most $O(poly(\log(a), \log(b), \log(Q)))$, and finding the continued fraction is also $O(poly(\log(a), \log(b), \log(Q)))$. Hence the entire running time must be $O(poly(\log(a), \log(b), \log(Q)))$.


