---
layout: post
_title: Orders and Primitive roots
---

# Theory
We know what **Fermat's little theorem** states.
<div class='theorem' text='Fermats Little Theorem'>
If $p$ is a prime number, then for any integer $a$, the number $a^p − a$ is an integer multiple of $p$. In the notation of modular arithmetic, this is expressed as
\[a^{p}\equiv a{\pmod {p}}.\]
</div>
So, essentially, for every $(a,m)=1$, ${a}^{\phi (m)}\equiv 1 \pmod {m}$. But $\phi (m)$ isn't necessarily the smallest exponent. For example, we know $4^{12}\equiv 1\mod 13$ but so is $4^6$.

So, we care about the "smallest" exponent $d$ such that $a^d\equiv 1\mod m$ given $(a,m)=1$.
# Orders
<div class='definition' text='order'>
Given a prime $p$, the order of an integer $a$ modulo $p$, $p\nmid a$, is the smallest positive integer  $d$, such that $a^d \equiv 1
\pmod p$. This is denoted $\text{ord}_p(a) = d$.
</div>

<div class='lemma'>
If $p$ is a primes and $p\nmid a$, let $d$ be order of $a$ mod $p$. Then $a^n\equiv 1\pmod p\implies d|n$.
</div>

<div class='proof'>
Let $n=pd+r, r\ll d$. Which implies $a^r\equiv 1\pmod p.$ But $d$ is the smallest natural number. So $r=0$. So $d|n$.
</div>

<div class='example'>
Show that $n$ divides $\phi(a^n-1)$ for $n>2, a>2$.
</div>

<div class='proof'>
Note that $\gcd(a,a^n-1)=1$. Moreover, order of $a\pmod {a^n-1}$ is $n$. But $a^{\phi{a^n-1})}\equiv 1 \pmod {a^n-1}.$ So, $n|\phi{a^n-1}$.
</div>

<div class='example'>
Determine all $n$ such that $n | 2^n -1$
</div>

We use a very common "trick". Which is to select the smallest prime $p$ which divides $n$. 
<div class='proof'>
Clearly $n$ is odd. \newline 
The main thing to observe here is,
$\gcd(p -1, n) = 1$ and so $ord_p (2)$ must equal $1$ as $p|2^n-1\implies \text{ord}_p(2)|n$ but $\text{ord}_p(2)|\phi(p)=p-1\implies \text{ord}_p(2)|\gcd(n,p-1)=1\implies p|2-1=1 $. And $n=1$ works and is the only solution.
</div>
<div class='example'>
Prove that every divisor of $2^p - 1$ is greater than $p$.
</div>

Well, let's just try for every prime divisor. If we can show it for prime divisor then we are done!

<div class='proof'>
Let $q|2^p-1$. The $\text{ord}_q(2)=1\text{ or } p$. If $1$ then $q|1$, not possible. So $\text{ord}_q(2)=p\implies p|q-1\implies p\ll q-1\ll q  .$
</div>

<div class='example'>
Prove that any prime factor of $2^{2^n} + 1$ is congruent to $1$ modulo $2^{n+1}$ .
</div>

<div class='proof'>
Say $p|2^{2^n} + 1$. So $$2^{2^n}\equiv -1\pmod p\implies 2^{2^{n+1}}\equiv 1\pmod p$$
$$\implies \text{ord}_p(2)=2^{n+1}\implies 2^{n+1}|p-1\implies p\equiv 1 \pmod {2^{n+1}}.$$
</div>
<div class='remark'>
Could you figure out how we concluded $ord_p(2)=2^{n+1}$?  
</div>

So, these are essentially all the tricks using just orders. Let's go to something new called "primitive roots".
# Primitive Roots
<div class='definition' text='primitive roots'>
Given a positive integer $n$. If $\text{ord}_n(g) = \phi(n)$ then $g$ is a primitive root modulo $n$.
</div>

<div class='problem'>
What is the primitive root of $3$? What about $4$? What about $8$? What about $15$?
</div>


The thing is, primitive roots do not exist for every number. Infact, there is a nice classification of numbers who have primitive roots. 

<div class='theorem'>
A primitive root exists modulo $n$ if and only if $n = 1, n = 2, n = 4$ or if $n$ is in the form $p^k$ or $2p^k$ for some positive integer $k$ and odd prime $p$.
</div>

We will not prove it here. The proof is very famous and can be found in any Undergraduate Number theory textbook.

Now, primitive roots are really special and they have pretty nice properties.
<div class='lemma'>
Given a prime $p$ and a primitive root $g$ modulo $p$, the set $\{g^1,g^2,\dots, g^{p-1}\}$ forms a complete set of residues modulo $p$.
</div>

<div class='proof'>
Suppose not. By Php, there exists $g^i\equiv g^j\pmod p$ and $i\le j\le p. $ 
Then $g^{j-1}\equiv 1\pmod p$ and $j-1\le p-1$. Not possible unless $j=i$.
</div>

<div class='theorem'>
Given a prime $p$, then $$(p - 1)! \equiv -1 \pmod p.$$
</div>


<div class='proof'>
Note that $$(p-1)!\equiv (p-1)(p-2)\dots 1 \equiv g^1\dot g^2 \dots g^{p-1}$$ $$g^{\frac{p(p-1)}{2}}\pmod p$$ $$(-1)^p\equiv -1 \pmod p$$
</div>

<div class='remark'>
Why is $g^{(p-1)/2}\equiv -1\pmod p$?
</div>

# Some important lemmas(?)

<div class='theorem'>
If $p$ is a prime. Then for any integer $x$, 
$$1^x+2^x+3^x+\dots+(p-1)^x\equiv 0 \pmod p\text{ if } p-1\nmid x, .$$ It is $0$ when $p-1\mid x$.
</div>
<div class='proof'>
Note that $$1^x+2^x+3^x+\dots+(p-1)^x\equiv g^x+g^{2x}+\dots+g^{(p-1)x}$$ $$\equiv g^x\cdot \frac{g^{(p-1)x}-1}{g^x-1}\pmod p.$$
If $p-1\nmid x$ then it is $0$. However, for $p-1|x$ we get denominator to be $0,$ but then just putting that in the original form gives us $p-1$ $1$'s. So $p-1$.
</div>

<div class='problem'>
Show that there are exactly $\phi(p - 1)$ primitive roots modulo $p$.
</div>

<div class='proof'>
Well, let us fix primitive root $g$. Then other primitive roots will be of the form $g^k$. For $g^k$ to be a primitive root, Note $\gcd(k,p-i)$. (why?). And it is a sufficient codition. So $\phi(p-1)$ such roots.
</div>

<div class='theorem' text='fermats christmas theorem'>
Let $p$ be an odd prime. Then there exists an integer $n$ such that $p | n^2 + 1$ if and only if $ p \equiv 1 \pmod 4$
</div>
<div class='proof'>
Let $$p|n^2+1\implies n^2\equiv -1\pmod p\implies n^4\equiv 1\pmod p\implies \text{ord}_p(n)=4.$$
So $4|p-1\implies p$. So $p\equiv 1\pmod 4$.
For other direction, we know that there exists a primitive root $g$. Note that $$g^{(p-1)/2}\equiv -1\pmod p.$$ Let $n=\pm (p-1)/4\pmod p$. That works.
</div>

<div class='definition'>
We begin with something called $v_p$. It is the p-adic evaluation of a number modulo $p$. If $p^k|a$ and $p^{k+1}\nmid a$ then $v_p(a)=k$.
</div>

Note the general properties:

* $v_p(xy)=v_p(x)+v_p(y)$
* $v_p(x+y)\ge \min( v_p(x),v_p(y))$. If $v_p(x)\ne v_p(y)$ then equality holds.


<div class='theorem'>
$$v_p(a^n-b^n)=v_p(n)+v(a-b)$$ if 
* $p|a-b, p\ne 2$ an odd prime
* $p\nmid a,b$

</div>
<div class='proof'>

We use induction on $v_p(n).$ [ We show for $v_p(n)=0, v_p(n)=1$ and then use induction.

1. We show it for $v_p(n)=0.$ That is show $v_p(x^n-y^n)=v_p(x-y)$
To show this is true, $$v_p(\frac{x^n-y^n}{x-y})=v_p(x^{n-1}+yx^{n-2}+y^2x^{n-3}+\dots+y^{n-1})=0.$$
As $x\equiv y\pmod p.$
So,  $$x^{n-1}+yx^{n-2}+y^2x^{n-3}+\dots+y^{n-1}\equiv nx^{n-1}\pmod p. $$
And $p\not\mid nx^{n-1}$

2. We show it for $v_p(n)=1.$ That is show $v_p(x^n-y^n)=v_p(x-y)+1$
To show this is true, $$v_p(\frac{x^n-y^n}{x-y})=v_p(x^{n-1}+yx^{n-2}+y^2x^{n-3}+\dots+y^{n-1})=1.$$
As $x\equiv y\pmod p\implies x=y+pk$
So,  $$x^{n-1}+yx^{n-2}+y^2x^{n-3}+\dots+y^{n-1}\pmod {p^2} $$
$$\equiv (pk+y)^{n-1}+(pk+y)^{n-2}y+(pk+y)^{n-3}y^2+\dots+y^{n-1}\pmod {p^2}$$
$$\equiv (y^{n-1}+pk\cdot (n-1)y^{n-2})+(y^{n-1}+ypk\cdot (n-2)y^{n-3})+\dots+y^{n-1}\pmod {p^2}$$
$$\equiv n\cdot y^{n-1}+pky^{n-2}\frac{(n-1)(n)}{2} \pmod {p^2}$$
Since $(n,p^2)=p.$ Let $n'=n/p.$
$$\equiv n'\cdot y+k\frac{(n-1)(n)}{2} \pmod {p}$$
but $p\not \mid n'\cdot y+k\frac{(n-1)(n)}{2}$

3. Let's assume it's true for $v_p=0,1,\dots, j-1.$ Now, we will show it's true for $v_p(n)=j.$
Then let $n=p^j\cdot c.$
Then $$v_p(x^n-y^n)=v_p(x^{p^j\cdot c}-y^{p^j\cdot c})=v_p((x^{p})^{p^{j-1}\cdot c}-(y^{p})^{p^{j-1}\cdot c})$$
$$=v_p(x^p-y^p)+v_p(p^{j-1}\cdot c)=v_p(x-y)+1+j-1=v_p(x-y)+v_p(n)$$

</div>

# Problems 

<div class='problem' text='putnam 1976 B6'>
As usual, let $\sigma (N)$ denote the sum of all the (positive integral) divisors of $N.$ (Included among these divisors are $1$ and $N$ itself.) For example, if $p$ is a prime, then $\sigma (p)=p+1.$ Motivated by the notion of a "perfect" number, a positive integer $N$ is called "quasiperfect" if $\sigma (N) =2N+1.$ Prove that every quasiperfect number is the square of an odd integer.
</div>
<div class='proof' text='proof by metricpaper at AoPS'>
Let $n=p_1^{e_1}\dots p_k^{e_k}$ be the prime factorization of $n$. Then we have$$\sigma(n)=\prod_{i=1}^k (1+p_i+p_i^2+\dots+p_i^{e_i}),$$so for any odd prime $p_j$, if $e_j$ is odd, then $(1+p_j+\dots+p_j^{e_j})$ is even, contradiction since $\sigma(n)$ is odd.

Thus we have $n=2^e m^2$ for some non-negative integer $e$ and odd positive integer $m$. Now$$\sigma(n)=(2^{e+1}-1)\sigma(m^2)=2^{e+1}m^2+1.$$

From this we get$$(2^{e+1}-1)(\sigma(m^2)-m^2)=m^2+1.$$If $e>0$, then $2^{e+1}-1\equiv 3\pmod{4}$, so $2^{e+1}-1$ has at least one prime divisor $p$ that is $3\pmod{4}$. By Fermat's Christmas Theorem, this is a contradiction, since $p\mid m^2+1$. Thus $e=0$, and $n=m^2$.
</div>

<div class='problem' text='IMO 1990/3'>
Determine all integers $ n > 1$ such that
$$\frac {2^n + 1}{n^2}$$ is an integer.
</div>
                                     
<div class='proof' text= 'proof by Shreyasharma at Aops'>
First note that all even $n$ fail, and $n = 1$ can be checked to work. Now we wish to determine all $n$ such that $2^n \equiv -1 \pmod{n^2}$. Take the smallest prime $p \mid n$. Then we require,
\begin{align*}
2^{2n} \equiv 1 \pmod{p}
\end{align*}Hence $\text{ord}_p(2) \mid \gcd(2n, p - 1)$. Note that $p-1$ and $n$ are coprime and hence $\gcd(2n, p - 1) = 2$, as $p > 2$. Now take cases.

First if $\text{ord}_p(2) = 1$ we require,
\begin{align*}
2 \equiv 1 \pmod{p}
\end{align*}which obviously fails. Then we must have $\text{ord}_p(2) = 2$ and hence,
\begin{align*}
4 \equiv 1 \pmod{p} \implies p = 3
\end{align*}Thus we have $n = 3k$ for some $k$. Then our desired condition becomes,
\begin{align*}
9k^2 \mid 8^k + 1
\end{align*}Now we can use LTE to find $\nu_3(8^k + 1) = 2 + \nu_3(k)$. However we also have $\nu_3(9k^2) = 2 + 2\nu_3(k)$. Clearly then we must have,
\begin{align*}
2 + \nu_3(k) \geq 2 + 2\nu_3(k) \iff 0 \geq \nu_3(k)
\end{align*}whence equality must occur. Thus $k$ is relatively prime to $3$. Now take the smallest prime $p \neq 3$ dividing $k$. Then we must have,
\begin{align*}
8^{2k} \equiv 1 \pmod{p}
\end{align*}Then $\text{ord}_p(8) \mid \gcd(2k, p-1)$. Clearly $\gcd(k, p-1) = 1$ and hence $\text{ord}_p(8) \mid 2$. Taking cases once more we can easily see that both imply that $7 \mid k$. However if $7 \mid k$, then we can easily see that $8^k + 1 \equiv 2 \pmod{7}$, a contradiction. Thus $k$ has no prime divisors, and thus $k = 1$. Therefore $n = 3k = 3$.

Then our final solution set is $\boxed{n = 1 \text{ and } n = 3}$.
</div>

<div class='problem' text='Romanian TST 1996'>
Find all primes $ p,q $ such that $ \alpha^{3pq} -\alpha \equiv 0 \pmod {3pq} $ for all integers $ \alpha $.    
</div>
<div class='proof' text='proof by th1nq3r at AoPS'>
First notice how $3, p, q$ are distinct. Assume $p = q$. Then $n^{3p^2} \equiv n \pmod{p^2}, \forall n \in \mathbb{Z^+}$. However if $n = p$, then we have that $p^{3p^2} \equiv p \pmod{p^2} \implies p^{3p^2 - 1} \equiv 1 \pmod{\frac{p^2}{\operatorname{gcd}(p, p^2)}} \implies 0 \equiv 1 \pmod p$, which is nonsense.

Now let $g_1, g_2$ be primitive roots modulo $p, q$ respectively. Then $g_1^{3qp} \equiv g_1 \pmod p \implies p - 1 \mid 3pq - 1$. Similarly $q -1 \mid 3pq - 1$. Thus we have that $p - 1 \mid 3q - 1$ and $q - 1 \mid 3p - 1$.

Let $3q - 1 = x(p - 1), 3p - 1 = y(q - 1)$, for some $x, y \in \mathbb N$. Now notice that $1 \leq x \leq 3$. If $x = 1$, we have that $3q - 1 = p - 1 \implies 3q = p$, which is absurd. If also $x = 3$, we have $3q - 1 = 3p - 3$. Reducing modulo $3$ gives us $2 \equiv 0 \pmod 3$. Another fallacy. Hence $x = 2$. Now then $3q - 1 = 2p - 1$ and $3p - 1 = y(q - 1)$. Solving for $q$ in the system of equations gives us $q = \frac{2y + 1}{2y - 9}$. Now $\frac{2y + 1}{2y - 9} = 1 + \frac{10}{2y - 9}$. Thus $y = 5, 7$. If $y = 5$ then $q = 11$ and $p = 17$. If $y = 7$, then $q = 3$ and $p = 5$. However $3, p, q$ are distinct, and so we can only have that $\boxed{(p, q) = (11, 17)}$ as the only solution.
</div>

<div class='problem' text='USATST 2008'>
Prove that for no integer $ n$ is $ n^7 + 7$ a perfect square.
</div>
<div class='proof' text='proof by Shreyasharma at AoPS'>
                                                
Note that it is easy to see $n \leq 0$ fail. Now take $n \geq 1$ and assume,$$n^7 + 7 = a^2$$for some square $a$. Now as perfect squares are $0$ and $1$ modulo $4$ we can easily show that $n \equiv 1 \pmod{4}$.
  
Then adding $121$ to both sides we wish to find solutions to$$n^7 + 2^7 = a^2 + 11^2$$Now we factor the left hand side to find$$(n+2)(\dots) = a^2 + 11^2$$and hence there exists some prime congruent to $3$ modulo $4$ dividing the right hand side. Hence there exists some prime $p$ dividing $a^2 + 11^2$. Now by Fermat's Christmas Theorem we must have $p \mid \gcd(a^2,11^2)$. However this implies that $\gcd(a^2, 11^2) > 1$ and namely $p = 11$. Then we have$$n^7 + 2^7 = 11^2(b^2 + 1)$$
Finally note that LTE gives,
\begin{align*}
\nu_{11}(n^7 + 2^7) = \nu_{11}(n+2)
\end{align*}
Then as the left hand side has an odd $\nu_{11}$ and the right hand side has an even $\nu_{11}$ we have reached our desired contradiction.
</div>

Well, hope you learnt something!
