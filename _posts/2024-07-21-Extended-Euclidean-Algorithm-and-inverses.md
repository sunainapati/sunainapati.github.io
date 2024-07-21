---
layout: post
_title: Extended Euclidean Algorithm and inverse
tags : Number-theory Abstract-algebra
---

How to find inverses of elements ( If you do not want to do computations)

I was reading Algebra:Ring theory and Field theory notes where I found the following exercise.

<div class='example'>
Suppose $\alpha \in \Bbb{C}$ is zero of $x^3-x+1$. Express $(\alpha)^{-1},(\alpha+1)^{-1}, (\alpha^2+1)^{-1}$ in terms of $a_0+a_1\alpha+a_2\alpha^2$ for $a_i\in\Bbb{Q}$.
</div>

**Working** : We know $Q[\alpha]\equiv Q[x]/\langle x^3-x+1\rangle$  which is a field.

So the above-mentioned should exist. We know $(\alpha)^{-1}$ can be expressed as $-\alpha^2+1$ and $(\alpha+1)^{-1}$ as $(-\alpha(\alpha-1))$. But I was not able to find $(\alpha^2+1)^{-1}$. 

Turns out, it is very simple. We use extended euclidean algorithm!

So 
$$ x^{3} - x + 1 = \bigg(x^{2} + 1\bigg)\bigg(x\bigg) + \bigg(-2 x + 1\bigg)$$
$$x^{2} + 1 = \bigg(-2 x + 1\bigg)\bigg(-\frac{1}{2} x - \frac{1}{4}\bigg) + \bigg(\frac{5}{4}\bigg)$$
$$-2 x + 1 = \bigg(\frac{5}{4}\bigg)\bigg(-\frac{8}{5} x + \frac{4}{5}\bigg) + \bigg(0\bigg)$$

$$\bigg(\frac{2}{5} x + \frac{1}{5}\bigg)\bigg(x^{3} - x + 1\bigg) + \bigg(-\frac{2}{5} x^{2} - \frac{1}{5} x + \frac{4}{5}\bigg)\bigg(x^{2} + 1\bigg) = 1$$

So inverse of $x^2+1$ is $$-\frac{2}{5} x^{2} - \frac{1}{5} x + \frac{4}{5}.$$

Alternatively, I liked [this explanation](https://math.stackexchange.com/posts/2959891) in StackExchange! 
