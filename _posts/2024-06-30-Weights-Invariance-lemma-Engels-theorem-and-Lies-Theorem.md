---
layout: post
_title: Weights, Invariance lemma, Engel's theorem and Lie's theorem
---

We are dealing with lie algebras
# Weights
<div class='definition'>
A weight for a lie subalgebra $A$ of $\text{gl(V)}$ is a linear map $\lambda:A\rightarrow F$ such that $$V_{\lambda}=\{v\in V: a(v)=\lambda(a)v\forall a\in A\}$$
</div>
Note that this is the generalisation of eigenvectors.

Note that $V_{\lambda}$ forms a vector subspace of $V$ as if $v,w\in V_{\lambda}$ then $$a(\alpha v+ \beta w)=a(\alpha v)+a(\beta w)=\alpha a(v)+\beta a(w)$$ $$\alpha \lambda(a)v+ \beta \lambda(a)w=\lambda(a)(\alpha v+\beta w).$$
<div class='problem'>
If $a, b : V \rightarrow V$ are commuting linear transformations and $W$ is the kernel of $a$, then $W$ is $b-$invariant.
</div>
<div class='proof'>
Let $w\in W$, then $$a(bw)=b(aw)=0\implies bw\in W.$$
</div>

# The invariance lemma
<div class='lemma'>
Suppose that $A$ is an ideal of a Lie subalgebra $L$ of $\text{gl}(V )$. Let $W = \{v \in V : a(v) = 0 \forall a \in A\}$.
Then $W$ is an $L$-invariant subspace of $V$ .
</div>
Here we use the famous trick that $ax=xa-[a,x]$
<div class='proof'>
Let $w\in W$ and $x\in L$. We have to show that $a(xw)=0 \forall a\in A$. Note that $$a(xw)=x(aw)+[a,x](w)=0.$$
</div>
<div class='theorem'>[Invariance lemma]
Assume that $F$ has characteristic zero. Let $L$ be a Lie subalgebra of $\text{gl}(V )$ and
let $A$ be an ideal of $L$. Let $\lambda : A \rightarrow F$ be a weight of $A$. The associated weight
space $$V_{\lambda} = \{v \in V : av = \lambda(a)v \forall a\in A\}$$
is an $L$-invariant subspace of $V$ .
</div>
<div class='proof'>
If $y\in L$ and $w\in V_{\lambda}$ then $y(w)\in V_{\lambda}$. That is, to show that $\forall a\in A, a(y(w))=\lambda(a)(y(w))$.

Again, using the above trick, we get $$a(yw)=y(aw)+[a,y](w)=y(\lambda(a)w)+\lambda([a,y])(w)=\lambda(a)yw+\lambda([a,y])(w).$$
So it is enough to show $\lambda([a,y])(w)=0$.

Consider $U=\text{span}\{w,y(w),\dots, y^{m-1}(w)\}$ such that they are linearly independent and hence  $w,y(w),\dots, y^{m-1}(w)$ are basis of $U$.
<div class='claim'>
Let $z\in A$, then wrt the basis $w,y(w),\dots, y^{m-1}(w)$, $z$ is represented as an Upper triangular matrix with diagonal entries $\lambda(z)$.
</div>
<div class='proof'>
We prove it by induction on columns (from left to right). For our base case, it is true as $zv=\lambda(z)v$. For $yw$, note that $$z(yw) = y(zw) + [z, y]w=\lambda (z)(yw)+\lambda[z,y](w)$$ which is the second column. 

Say it is true till $k$ th column.  Hence, $$z(y^{r-1}w)=\lambda (z)(y^{r-1}w)+ u, u \in\text{ span}\{w,y(w),\dots, y^{r-2}(w)\}.$$
So $k+1$th colum will be $$z(y^rw)=zy(y^{r-1}w)=(yz+[z,y])(y^{r-1}w)=yzy^{r-1}w+[z,y]y^{r-1}w$$$$= \lambda (z)(y^{r}w)+ yu+ [z,y]y^{r-1}w$$
Since $[z,y]\in A $, we get $[z,y]y^{r-1}w=\lambda([z,y])y^{r-1}w\in \in\text{ span}\{w,y(w),\dots, y^{r-1}(w)\} $. So induction works.
</div>
Now take $z = [a, y]$. Note that the trace of the matrix of $z$ acting on $U$ is $m\lambda(z)$. $U$ is invariant under the action of $a \in A$, and $U$ is $y$-invariant by construction.
Note that trace is $0$. So $\lambda(z)=0$ as char is $0$. So done. We proved it.
</div>

<div class='problem'>
Let $x, y : V \rightarrow V$ be linear maps from a complex vector space $V$ to itself.
Suppose that $x$ and $y$ both commute with $[x, y]$. Then $[x, y]$ is a nilpotent map.  
</div>
<div class='proof'>
Note that if $\lambda$ be an eigen value of the linear map $[x,y]$. Let $W=\{v\in V:[x,y]v=\lambda v\}$ be the eigenspace. Note that it is a subspace of $V$.  

Let $L$ be the lie algebra of $\text{gl(V)}$ spanned by $x,y,$ and $[x,y]$. Note that span $\{[x,y]\}$ is an ideal of $L$. So the invariance lemma implies that $W$ is invariant under $L$. So it is invariant under $x$ and $y$.

Pick any basis of $W$ and let $X$ and $Y$ be the matrices of $x$ and $y$ wrt the basis. So $[x,y]=XY-YX$.
But every element of $W$ is an eigenvector of $[x,y]$ with eigenvalue $\lambda$. 
<div class='claim'>
$XY-YX$ is a scalar matricx with scalar $\lambda$ wrt the basis
</div>
However, taking trace, gives us $$0=\lambda \text{dim} W\implies \lambda =0.$$
<div class='claim'>
If a linear operator $\phi : V \rightarrow V$ on a vector space is nilpotent, then its only eigenvalue is $0$ And it similarly if only eigenvalues are $0$ then it is nilpotent.
</div>
<div class='proof'>
Let $A$ be a nilpotent, so $A^n = 0$ for some $n$.  Now let $v$ be an eigenvector: $A v = \lambda v$ for some scalar $\lambda$.  Now we get
$$0 = A^n v = \lambda^n v\implies \lambda=0.$$
Other direction: Suppose that all the eigenvalues of the matrix $A$
 are zero. Then the characteristic polynomial of the matrix $A$
 is $$p(t)=det(A-tI)=\pm t^n\implies 0=p(A)=\pm A^n\implies A\text{ is nilpotent }.$$
</div>
So using the above claim, we are done.
</div>

# Engel's theorem
We will try to prove Engel's theorem. But what does it say? But first we state a common result in linear algebra.
<div class='theorem'>
Let $V$ be a $n$ dim vector space. And let $x:V\rightarrow V$ be a nilpotent map. Then there exists a basis of $V$ is which $x$ is a Upper triangular matrix.
</div>
<div class='proof'>
Since $x$ is nilpotent, $\exists N\in \Bbb{N}$ such that $x^N=0$. Now $0\ne v\in V\implies x^N(v)=0$. Let $m$ be smallest $m$ such that $w=x^{m-1}v\ne 0$. So $x(w)=0\implies w\in \text{Null}(x)$.

If $n=1$. Then $V=\text{span}(w)$ as $w\ne 0$. So the transformation $x$'s matrix wrt $w$ is $[0]$. Say the statement is true for any $k$ dimensional vector space. We will show that it is true for any $k+1$ dimensional vector space. 

Let $W=\text{span}w$ which is subspace of $V$. So $V/W$ is $k$ dimensional. 

Note that $\overline{x}$ is nilpotent as $\overline{x}=x+W$ and $$(\overline{x})^n=(x+W)^n=x^n+W.$$ And $x^n=0\in V, W\subseteq V$. So $(\overline{x})^n=0+W$. Hence nilpotent.

So, we apply induction hypothesis to $V/W$. We get a basis $\overline{B}=\{v_1+W,\dots,v_{k}+W\} $. Note that $\overline{x}(v_j+W)=\alpha_1v_+\dots+\alpha_{j-1}v_{j-1}+W$. Take the basis $B=\{w,v_1,\dots,v_k\}$. We get $x(v_j)=\alpha_0w+\dots+\alpha_{j-1}v_{j-1}$. And done! It satisfies the Upper triangular matrix!
</div>

<div class='theorem'>
Let $V$ be a vector space. Suppose that $L$ is a Lie subalgebra of $\text{gl}(V )$ such
that every element of $L$ is a nilpotent linear transformation of $V$ . Then there is a basis of $V$ in which every element of $L$ is represented by a strictly upper triangular matrix. 
</div>
<div class='proof'>
But before proving this, we prove the following lemma. 
<div class='lemma'>
Suppose that $L\subset \text{gl}(V)$ is such that every $x\in L$ is nilpotent. Then $\exists 0\ne v\in V$ such that $x(v)=0\forall x\in L$.
</div>
<div class='proof'>
 We do induction on $L$. Say dim $L$ is $1$. Then by the above we showed that there is some non zero $v\in V$ such that $z(v)=0$. But $L$ is spanned by $z$. Then done. 

 Say it is true for all lie algebra of dimension upto $k$. Suppose dim $L=k+1$.
<div class='claim'>
There is an ideal $I\subset L$ such that dimension of $I$ is $k$.
</div>
<div class='proof'>
Let $A$ be maximal lie subalgebra of $L$. Consider $L/A$.

Consider the linear map $\overline{ad}:A\rightarrow \text{gl}(L/A)$ such that $$\overline{ad}_{a}(x)=[a,x]+A.$$
<div class='claim'>
 $\overline{ad}_{a}$ is a lie homorphism.
</div>
<div class='proof'>
To show it is a homorphism, note that $$\overline{ad}(\alpha a+\beta b)=\alpha\overline{ad}(a)+\beta \overline{ad}(b).$$
Note that $$\overline{ad}(\alpha a+\beta b)(x)=[\alpha a+\beta b,x]+A=\alpha[a,x]+\beta[b,x]+A$$ $$=\alpha\overline{ad}(a)+\beta \overline{ad}(b).$$
To show it is a lie homorphism, we have to show $$\overline{ad}([a,b])=[\overline{ad}(a),\overline{ad}(b)].$$
Or show $$ \overline{ad}([a,b])(x)=[\overline{ad}(a),\overline{ad}(b)](x)$$
But LHS is $[[a,b],x]+A$ and RHS is $$(\overline{ad}(a)\cdot \overline{ad}(b) - \overline{ad}(b)\cdot \overline{ad}(a))(x) $$
$$=[a,[b,x]]-[b,[a,x]]+A=[a,[b,x]]+[b,[x,a]]+A=-[x,[a,b]]+A=[[a,b],x]+A.$$
</div>
So $$\text{img}(\overline{ad})\subset \text{gl}(L/A)\implies  \text{dim img}(\overline{ad})\le dim (A)<dim L=k+1.$$
So $  \text{dim img}(\overline{ad})\le k$ and $a\in A\text{ is nilpotent}\implies ad(a) \text{ is nilpotent}\implies \overline{ad}(a) \text{ is nilpotent}.$
So $\text{img}(\overline{ad})$ satisfies induction hypothesis. Hence there exists $y+A\ne 0\in L/A$ such that $$(\overline{ad})_a(y+A)=0\forall a\in A\implies [a,y]+A=0\implies [a,y]\in A\forall a\in A.$$
Note if $A\subset A\bigoplus Fy\subset L$ then since $A$ has maximum dimension we get that $A\bigoplus Fy=L\implies dim A=dim L-1$ and note that $A$ is ideal here. 
</div> 
So $L=A\bigoplus Fy$. So $dim(A)=k$. We apply induction hypothesis on $A$. So there exist $0\ne u\in V$ such that $a(u)=0\forall a\in A$. 

Let $W=\cap_{a\in A} \text{Null}(A)$. Note $u\in W$.

By invariance lemma, $W$ is invariant under $L$. So $y(W)\subset W$. But $y$ is nilpotent. So is $y$ restricted over $W$ is nilpotent.Hence $\exists v\in W$ such that $y(v)=0$.
Since $$L=A\bigoplus Fy\implies x=a+By, a\in A, B\in F\implies x(v)=a(v)+By(v)=0\forall x\in L.$$
</div>
We use induction on $L$. If dim $L=1$. Then $L$ is spanned by a vector $x$. Then $x$ is representable as a Upper triangular matrix. So done.

Suppose $\forall$ lie algebra of dim $\le k$, the statement is true. Say dim $L=k+1$.

We showed that $\exists 0\ne u\in V$ such that $x(u)=0\forall x\in L$. Set $U=span\{u\}$. And let $\overline{V}=V/U$. Consider the map $L\rightarrow gl(\overline{V})$ such that $x\in L\rightarrow \overline{x}$.

Note that the image of the map is subset of $\text{gl}(\overline{V})$. Moreover $\overline{V}$ has dimension $k$. So $\exists$ basis of $\overline{V}$ such that all $\overline{x}$ are upper triangular. Hence $\{v_1+U,\dots,v_{k}+U\}$.
Then $\{u,v_1,\dots,v_k\}$ is a basis of $V$. As $x(u)=0$, we get that $x$ is strictly upper triangular.

</div>

#  second version of Engel's theorem
<div class='theorem'>
A Lie algebra $L$ is nilpotent if and only if for all $x \in  L$ the linear map $ad x :L \rightarrow $ is nilpotent.
</div>
<div class='proof'>
 If $L$ is nilpotent then $\exists N\in \Bbb{N}$ such that $L^N=0$. Then $[[[\dots [x[x,\dots [x,y]\dots ]\in L^N=0\implies (adx)^{N-1}(y)=0\implies (adx)^{N-1}=0$.

 Let $\overline{L}=ad~L$. $ad:L\rightarrow \text{gl}(L)$. Every element of $\overline{L}$ is nilpotent. So $\exists$ basis such that $ad~x$ is upper triangular strictly. 
 
 So $\overline{L}$ is nilpotent. (as when we commute two Upper triangular matrix, we get 2nd upper diagonal to be 0s and so on).
 Since $\overline{L}$ is nilpotent, then so is $L/Z(L)\cong \overline{L}$. Hence $L$ is nilpotent.
</div>
<div class='remark'>
 Converse of Engel's theorem is not true. Let $I$ denote the identity map in gl$(V )$. The Lie subalgebra Span $\{I\}$ of gl(V ) is nilpotent.It is (trivially) nilpotent as it is spanned by one vector  and $[x,x]=0$. 
 In any basis of V , the map $I$ is represented by the identity matrix, which is certainly not strictly upper triangular.
</div>

# Lie's theorem
<div class='theorem'>
 Let $V$ be an $n$-dimensional complex vector space and let $L$ be a solvable Lie subalgebra of $\text{gl}(V )$. Then there is a basis of $V$ in which every element of $L$ is represented by an upper triangular matrix.
</div>

<div class='claim'>
Suppose $V\equiv \Bbb{C}^n$ and $x\in \text{gl}(V)$. Then $\exists$ a basis of $V$ such that $x$ is upper triangular matrix.
</div>
<div class='proof'>
We begin with the claim
<div class='claim'>
 $x$ has an eigenvector
</div>
<div class='proof'>
Take any $0\ne v\in V$ and consider$\{v,xv,x^2v,\dots, x^mv\}$ where $m$ is the minimum such that the vectors are linearly dependent. So $\exists \alpha_0,\dot,\alpha_m$ such that $\alpha_m\ne0$. We can factor over $\Bbb{C}$. So $$\alpha_m(x-\lambda_0I)\dots (x-\lambda_mI)v=0.$$ Take $k$ to be minimum such that $w=(x-\lambda_{k+1}I)\dots (x-\lambda_mI)v=0$. Now, $(x-\lambda_kI)w=0\implies xw=\lambda_kw$.
</div>
Now we try to prove by induction on dimension of $V$. Say it is true for all dimensions less than or equal to $k$. Let $w\in V$ be an eigenvector of $x$ with value $\lambda$.

Consider $x:V\rightarrow V$ and $\overline{x}:V/{\Bbb{C}w}\rightarrow V/{\Bbb{C}w}$. And $\overline{x}(v+\Bbb{C}w)=x(v)+\Bbb{C}w$.
So dim$(V/\Bbb{C}w)=k$. We apply induction hypothesis to $V/\Bbb{C}w$. Then there is a basis $\{v_1+\Bbb{C}w,\dots, v_{k+1}+\Bbb{C}w\}$. Then the basis of $V$ as $\{w,v_1,\dots,v_{k+1}\}$ works. 
</div>
<div class='lemma'>
Let $V$ be a non-zero complex vector space. Suppose that $L$ is a solvable Lie subalgebra of $gl(V )$. Then there is some non-zero $v\in V$ which is a simultaneous eigenvector for all $x \in L$.
</div>
<div class='proof'>
 We do Induction on dim $L$. If $1$ then say it is spanned by $x$. Since $x\in \text{gl}(v)$ it has an eigenvector. So done.

 Suppose the statement holds for all lie algebra of dim $k$ and dim $L=k+1$.

 Since $L$ is solvable $\implies L^{(N)}=0$ for some $N\in \Bbb{N}$. Note $L'\subset L$ and $L'\ne L$ else $L^{(N)}=L\forall n$. 

 Choose a subspace $A$ of $L$ which contains $L'$ and is such that $L = A \bigoplus Span\{z\}$ for some $z\in L$.
 <div class='claim'>
  $A$ is ideal of $L$.
 </div>
<div class='proof'>
$$x\in L, a\in A,[x,a]\in [L,L]=L'\subset A'.$$
</div>
dim $A=k$, $A$ is solvable. By inductive hypothesis $\implies \exists w\in V$ $w$ is eigenvector for all $a\in A$.

$$\lambda:A\rightarrow \Bbb{C}$$
$$aw=\lambda(a)w$$
$$V_\lambda=\{v\in V| a(v)=\lambda(a)v\}$$
So by invaraince lemma, we get that $V_{\lambda}$ is $L$invariant. So $x(v)\in V_{\lambda}\forall v\in V_{\lambda}$. So $\exists u\in V_{\lambda}$ which is eigenvector of $z\in V$. Let $z(u)=\mu (u)$. $\forall x\in L, x=\alpha +\beta z$
$$x(u)=\alpha(u)+\beta z(u)=\lambda(\alpha)u+\beta\mu(u)\forall x.$$
So done!
</div>

So now the main proof.
<div class='proof'>
 We do induction $V$. For dim $1$ it is good. Say true for $k$. Now for $k+1$. It is essentially same as engel's theorem.

 Find $w\in V$ such that $w$ is eigenvector for all $x\in L$.
 $$\implies x(w)=\lambda(x)w, \lambda:V\rightarrow \Bbb{C}.$$
 Define $$\overline{x}(V+\Bbb{C}w)=x(v)+\Bbb{C}w.$$
 Consider $Im(\overline{x})\subset\text{gl}(V/\Bbb{C}w)$. So we use induction hypothesis, get a basis $\{v_1+\Bbb{C}w,\dots, v_k+\Bbb{C}w\}$. So let the basis be $\{w,v_1,\dots, v_k\}$.
</div>
