---
layout: post
_title: Simpler Fisher Inequality
tags : Coding-theory
---

This problem is one of the few problems we discussed in the tutorial for Graduate Mathematical toolkit 2026 which I am TAing along with Avishek. The post is named "Simple Firsher inequality" because it is indeed a simpler Fisher's ienquality, which states that 
" Let $k$ be a positive integer. In a town with $n$ people, $m$ clubs have been formed. Every two clubs share exactly $k$ members. Prove that $m\le n$." The proof of this is essentially the same as the simpler version and we have left it as a nice cute exercise :) 

<div class="problem">
Students in a school go for ice cream in groups of at least two. After $k > 1$ groups have gone, every two students have gone together exactly once. Prove that the number of students in the school is at most $k$.
</div>
In the tutorial, we all came up with various conditions and various encodings for this problem.
I think when you first see this problem, you try to come up with the graph theoretic. You would like to make the adajceny matrix of graph where verties are students and edges are labelled by the groups they have in common (note, it is just 1).
However, after that, you start seeing things feel very double counting. Here are two linear algebraic solutions to this problem. They sort of help you think linear algebraically. And as a great mathematican once said, combinatorics is just linear algebra.

In our solution, our set up is going to be the same. Let students be $s_1,\dots,s_n$. Let groups be $G_1,\dots,G_k$.  
For each student $s_i$, we will associate a $k$ lenght tuple, $v_i$ such that $v_{ij}=1\iff s_i\in G_j$. And similarly, for each group $G_j$ define $w_j$ to be vector of $n$ lenght with $w_{ji}=1\iff i\in G_j$. So, we have $\langle w_j,wj\rangle\ge 2$, $\langle v_{i'},v_j\rangle =1$ and $\langle w_{j'},w_j\rangle \le 1$. Now, the proof of Solution, relies on one more simple observation. That is, $\langle v_i,v_i\rangle \ge 2$. That is because, if it was $1$. Then student $i$ is only in one group, but then all pair involving student $i$ must be in that group. Hence, all students are in this group. So only one group is present. But $k>1$.

<div class="proof">
It follows closely to what Yufei's solution is. We claim that $v_1,\dots,v_n$ are linearly independt in $\Bbb R^k$. Suppose $\sum_i c_i v_i = 0$ in $\mathbb{R}^k$. Then
$$0 = \langle \sum_i c_iv_i,\sum_i c_iv_i\rangle = \sum_i c_i^2\langle v_i,v_i\rangle + \sum_{i\ne i'} c_ic_{i'}\langle v_i,v_{i'}\rangle \ge \sum_i c_i^2 (\langle v_i,v_i\rangle) + \sum_{i\ne i'}c_ic_{i'}.$$
So $$0 = \sum_i c_i^2(\langle v_i,v_i\rangle-1) + \sum_i c_i^2(\sum_i c_i)^2\implies \sum_i $$
Note that $c_i^2((\langle v_i,v_i\rangle-1)\ge 0$ and the last term is $\ge0$. So  $c_i^2(\langle v_i,v_i\rangle-1)=0$ for all $i$. But $\langle v_i,v_i\rangle-1\ge 0\implies c_i=0$ for all $i$. So $v_1,\dots,v_n$ are linearly independent vectors over $\mathbb{R}^k$. Hence $n\le k$. So done.
</div>
