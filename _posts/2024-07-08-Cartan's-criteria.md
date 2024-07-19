---
layout: post
_title: Cartan's criteria for solvability and semi-simplicity and more on semi-simple lie algebra
tags : ["Lie algebra"]
---
Hi! Another lie algebra post. 
# Contents
{:.no_toc}

* A markdown unordered list which will be replaced with the ToC, excluding the "Contents header" from above
{:toc}

# Cartan's criteria for solvability
<div class='theorem'>
 Suppose $L$ is a complex solvable lie algebra. Then $L$ is solvable iff $\forall x,y,z\in L,k([x,y],z)=0$
</div>
<div class='proof'>
 Suppose $L$ is solvable. Then consider $ad:L\rightarrow gl(L)$. Note that $im(ad)$ is a quotient and homomorphism of $L$, hence solvable. So there exists a basis of $L$ such that $\forall w\in L$, $ad_w$ is upper triangular matrix. Hence $[ad_x,ad_y]$ is upper triangular matrix. Hence $[ad_x,ad_y]ad_z$ is is upper triangular matrix. So $Tr([ad_x,ad_y]ad_z)=0\implies k([x,y],z)=0$.

 Suppose $\forall x,y,z\in L,$ we have $k([x,y],z)=0$. We will show that $L'$ is nilpotent. Note that $w=[x,y]\in L'\implies k(w,z)=0$. We know that by jordan decomposition, $ad_w=(ad_w)_d +(ad_w)_n=W_d+W-n$. But note that $tr(W\cdot \overline{W_d})=tr(W_d\cdot \overline{W_d})=|\lambda_1|^2+\dots+|\lambda_m|^2$ and $\lambda_i$ is eigenvalue of $W$. 
 But $tr(W\cdot \overline{W_d})= tr(ad_{[x,y]}\cdot ad_{\overline{w}_d})= 0.$
 So the eigenvalues are $0$. So $L'$ is nilpotent. So $L$ is solvable.
</div>

# Cartan's criteria for semi simplicity
<div class='definition'>
 $W^{\perp}=\{x\in W|k(x,w)=0\forall w\in W\}$
 where $k$ is the killing form and $W$ is subspace of lie algebra $L$.
</div>
<div class='theorem'>
 If $I$ is ideal of $L$ then $I^{\perp}$ is ideal of $L$.
</div>
<div class='proof'>
 Let $x\in L$ and $j\in I^{\perp}$. We want to show $[j,x]\in I^{\perp}$. We want to show $$tr(ad_{[j,x]}\cdot ad_i)=0 \forall i\in I.$$
 But we know that $$tr([a,b]c)=tr(a[b,c]).$$ So $$tr(ad_{[j,x]}\cdot ad_i)=tr(ad_j\cdot ad_{[x,i]})\text{  but } [x,i]\in I\implies tr(ad_j\cdot ad_{[x,i]})=0.$$
</div>
<div class='theorem'>
 Suppose $L$ is a lie algebra over $\Bbb{C}$. Then $L$ is semi-simple $\iff$ $k$ is non-degenerate. That is if $x\ne 0\implies k(x,x)\ne 0.$ 
</div>
<div class='proof'>
 Suppose $L$ is semi-simple.So rad $L$ is $0$. So there is no solvable ideal of $L$. Note that $L\subset L$ is an ideal. Now take $x,y,z\in L^{\perp}\implies [x,y]\in (L^{\perp})'$. Note that $k([x,y],z)=0$ as $[x,y]\in L$. So $L^{\perp}$ is solvable (by the criterion) and ideal. So $L^{\perp}=0$. Hence $k$ is non-degenarate. 
 \newline
 Other way: Say $L$ is not simple $\implies$ it has solvable ideals. Take $0\ne I\subset L$ a solvable ideal $\implies \exists N\in \Bbb{N}$ such that $I^{(N)}=0$ and $I^{(N-1)}\ne 0$. Let $A=I^{(N-1)}$. Now $\forall y\in I$ we have $$ad_aad_xad_a(y)=[a,[x,[a,y]]]=0\implies (ad_aad_x)^2=0$$$$\implies ad_a\cdot ad_x\text{ is nilpotent }\implies tr(ad_a\cdot ad_x)=0\implies k(a,x)=0\implies k(a,a)=0.$$
</div>

# Why is it called semi-simple 
Now, we will understand why it is called semi-simple!
<div class='theorem'>
 Let $L$ is a lie algebra over $\Bbb{C}$. Then $L$ is semisimple $\implies \exists$ simple ideals $L_1,\dots, L_n\subset L$ such that $L=L_1\bigoplus\dots \bigoplus L_n$.
</div>
<div class='proof'>
We do induction on dim $L$. Base case: dim $L=1\implies L$ is simple. 
Say for all lie algebras of dim $\le m-1$, the statement holds and dim $L=m$.
Let $I\subset L$ be ideal of $L$ and minimal dimension. If $I=L$ then $L$ is simple. If $I\ne L$ then we have the following claim.
<div class='claim'>
 $$L=I\bigoplus I^{\perp}, I,I^{\perp}\text{ are semi-simple }.$$
</div>
<div class='proof'>
Note that $$x\ne 0\in I\cap I^{\perp}\implies k(x,x)=0\implies k \text{ is degenerate}\implies x =0.$$
Note that $I,I^{\perp}$ commute. $$[x,w]\in I,I^{\perp}\implies [x,w]=0\forall x,w \in I,I^{\perp}.$$
Note that $L=I+I^{\perp}$ as $I\rightarrow I\rightarrow \Bbb{C}$ is isomorphism. So $V\rightarrow I\rightarrow \Bbb{C}$ is surjective and kernel is $I^{\perp}$. And dimensions follow!
They are semi-simple, because suppose $J\subset I$ is a solvable ideal. Then $$[J,I^{\perp}]\subset [I,I^{\perp}]=0\implies J\subset I^{\perp} \text{ and solvable}.$$ Not possible. So both are semi-simple.
</div>
Now use induction on $I^{\perp}$.

Other direction: Suppose $$L=L_1\bigoplus\dots \bigoplus L_n.$$ Let $I=radL$. Let $I_k=[I,L_k]$. Note that $I_k\subset L_k$ a solvable ideal. So $I_k=0$. So $$[I,L]=[I,L_1\bigoplus \dots L_n]\subset I_1\bigoplus\dots \bigoplus I_n=0$$ $$\implies I\subset Z(L)\subset Z(L_1)\bigoplus Z(L_n)=0.$$
</div>

