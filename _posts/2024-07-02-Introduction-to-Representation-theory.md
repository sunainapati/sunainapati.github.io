---
layout: post
_title: Introduction to Representation theory
---

We are dealing with lie algebras.

# Homorphism theorems
<div class='definition'>
Let $L$ be a Lie algebra and let $V$ and $W$ be $L-$modules. An $L-$module homomorphism or Lie homomorphism from $V$ to $W$ is a linear map $\theta : V \rightarrow W$ such
that $\theta(x \cdot v) = x \cdot {\theta(v)}$ for all $v \in V$ and $x \in L$.
</div>
An isomorphism is a bijective $L-$module homomorphism.
<div class='remark'>
 This makes sense because $x\cdot v\in V$ and $\theta v\in W$. So $x\cdot \theta (v)$ is also in $W$. And it is using that it is $L-$module.
</div>

# Schur's lemma 
<div class='theorem'>
Let $L$ be a complex lie algebra and $V$ be a finite dimensional  simple $L-$ module where $\theta:V\rightarrow V$ is an $L-$module homomorphism. Then $\theta=\lambda\text{id}_V$ for some $\lambda\in \Bbb{C}$.
</div>
<div class='proof'>
 Since we are working in $\Bbb{C}$, let $\lambda\in\Bbb{C}$ be an eigenvalue of $\theta$. Let $v\in V$ be the corresponding eigenvector. So $$\theta(v)=\lambda v\implies v\in \text{Null}(\theta-\lambda\text{id}_V)\implies\{0\}=\text{Null}(\theta-\lambda\text{id}_V)\subset V \text{ is a submodule }$$ $$V= \text{Null}(\theta-\lambda\text{id}_V)\implies \forall u\in V, \theta(u)=\lambda(u)\implies \theta=\lambda\text{id}_V.$$
</div>
<div class='lemma'>
Let $L$ be a complex lie algebra and abelian. And $V$ be a simple finite dimensional module. Then $dim(V)=1$.
</div>
<div class='proof'>
We define $\theta_x:V\rightarrow V$ and $\theta_x(v)=x\cdot v$. Note that $\theta_x:V\rightarrow V$ is an $L-$module homorphsim. Note that $$y\cdot \theta_x(v)=y(x\cdot v)=x\cdot(y\cdot v)-[x,y]\cdot v=\theta_x(y\cdot v).$$ Since $L$ is complex and $\theta_x$ is $V\rightarrow V\implies \theta_x=\lambda_x\text{id}_V$. So $x\cdot v=\theta_xv=\lambda_xv\implies \text{span}v\subset V$ is submodule.
</div>
