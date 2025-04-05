---
layout: post
_title: Introduction to Coding theory
tags : Coding-theory
---
I have started learning coding theory and I thought of sharing the things I have learnt here! 
# Contents
{:.no_toc}

* A markdown unordered list which will be replaced with the ToC, excluding the "Contents header" from above
{:toc}

# Introduction 

Suppose two parties, Alice and Bob, wish to communicate over a channel that may be unreliable---that is, parts of the message may get corrupted or altered during transmission. To ensure robust communication, we want the recipient to be able to detect such corruption, and ideally, recover the original message even in the presence of errors.

We assume that the channel allows the transmission of strings over a fixed finite alphabet. This alphabet could be a finite field (e.g., $\mathbb{F}_q$), binary symbols (bits), or even characters from the English alphabet.

This brings us to two central goals in the design of such communication systems:

**Error detection**: Identifying whether the received message has been corrupted.
**Error correction**: Reconstructing the original message despite some level of corruption.


In many practical scenarios, the message that Alice wishes to send may be written in one alphabet—say, English—while the communication channel supports a different alphabet—such as binary strings. In such cases, we need a systematic way to convert messages from the source alphabet to the channel alphabet. This is typically done by encoding the message into blocks of symbols over the channel alphabet.

For instance, when converting English text to binary, we might use ASCII encoding. Each character is represented as a fixed-length binary string, i.e., a block of bits. These binary blocks are then transmitted over the channel.

Naturally, not every possible block of bits corresponds to a meaningful message. In general, only a subset of all possible strings is used for encoding valid messages. This leads us to the formal notion of a block code.

<div class="definition">
Let $\Sigma$ be the fixed finite alphabet used by the communication channel. A block code $\mathcal{C}$ of length $n$ over $\Sigma$ is a subset of $\Sigma^n$:
\[
\mathcal{C} \subseteq \Sigma^n.
\]
Elements of $\mathcal{C}$ are called codewords.
</div>

<div class="definition">
For any two strings $x$ and $y$ of the same length, the Hamming distance between them is defined as the number of positions at which the corresponding symbols differ. That is,
\[
d(x, y) = \left| \left\{ i \mid x_i \neq y_i \right\} \right|.
\]
</div>
Turns out Hamming distance is actually a distance!
<div class="theorem">
The Hamming distance defines a metric on \( \Sigma^n \).
</div>


Let \( x, y, z \in \Sigma^n \). We verify the four properties of a metric:
- **Non-negativity**: 
    By definition, \( d(x, y) \) counts the number of differing coordinates between \( x \) and \( y \). Since this is a count, \( d(x, y) \geq 0 \).

- **Identity of indiscernibles**:
    If \( x = y \), then all coordinates agree, so \( d(x, y) = 0 \).  
    Conversely, if \( d(x, y) = 0 \), then there are no positions \( i \) with \( x_i \neq y_i \), so \( x = y \).

- **Symmetry**:  
    The number of positions where \( x_i \neq y_i \) is the same as the number where \( y_i \neq x_i \), so  
    \[
    d(x, y) = d(y, x).
    \]

- **Triangle inequality**: 
    Let us consider each coordinate \( i \in \{1, 2, \dots, n\} \). At each position, define the indicator function:
    \[
    \delta(a, b) = 
    \begin{cases}
    1 & \text{if } a \neq b, \\
    0 & \text{if } a = b.
    \end{cases}
    \]
    Then,
    \[
    d(x, z) = \sum_{i=1}^n \delta(x_i, z_i).
    \]
    For each \( i \), observe that
    \[
    \delta(x_i, z_i) \leq \delta(x_i, y_i) + \delta(y_i, z_i),
    \]
    because if \( x_i = z_i \), the left-hand side is 0 and the inequality holds; and if \( x_i \neq z_i \), then either \( x_i \neq y_i \) or \( y_i \neq z_i \) (or both), so the right-hand side is at least 1. Summing over all \( i \), we get
    \[
    d(x, z) \leq d(x, y) + d(y, z).
    \]


Hence, all the properties of a metric are satisfied.



<div class="definition">
The distance of a code $\mathcal{C}$ is the minimum Hamming distance between any two distinct codewords in $\mathcal{C}$. Formally,
\[
d(\mathcal{C}) = \min_{\substack{x, y \in \mathcal{C} \\ x \neq y}} d(x, y).
\]
</div>

In a sense, the distance of a code quantifies how many changes are required to transform one valid message (codeword) into another. For example, if a code has distance $d = 5$, this means that there exist two distinct codewords $x$ and $y$ that differ in exactly 5 positions.

Now, suppose Alice sends the codeword $x$, but due to noise in the channel, exactly those 5 positions are altered. Then Bob would receive $y$ instead of $x$, and since $y$ is also a valid codeword, he would completely misinterpret the message. 

This highlights a key idea: to minimize the chance of such confusion, we want codes to have large distance. A larger distance makes it less likely that noise will transform one valid codeword into another. This leads to an important observation.

<div class="claim">
 Let $d$ be the distance of a code $\mathcal{C}.$ Then the code is
$d-1$-detectable, or if the channel corrupts atmost $d-1$ letters of
the message, then the other party can detect that the code word has
been corrupted.
</div>
<div class="proof">
 By definition, the minimum distance \( d \) of a code \( C \) is the smallest Hamming distance between any two distinct codewords in \( C \). This means that to transform one codeword into another, at least \( d \) symbol changes are required.

Suppose a codeword \( c \in C \) is transmitted, and at most \( d - 1 \) symbol errors occur during transmission. Let \( r \) be the received word. Then the Hamming distance between \( c \) and \( r \) is at most \( d - 1 \).

However, since any other codeword in \( C \) is at distance at least \( d \) from \( c \), the received word \( r \) cannot be a different valid codeword. Therefore, either \( r = c \), or \( r \notin C \).

Thus, if \( r \in C \), no errors occurred; otherwise, if errors occurred, \( r \notin C \), and the receiver can detect that an error happened.

Hence, the code can detect up to \( d - 1 \) errors.
</div>
<div class="lemma">
 If the communication channel corrupts at most $t$ symbols during transmission, then any code with minimum distance at least $t + 1$ can detect  such errors. That is, Bob can recognize when the received message has been corrupted.
</div>

<div class="theorem">[Error Correction Bound]
Let \( C \subseteq \Sigma^n \) be a code with minimum Hamming distance \( d \). Then \( C \) can correct up to \( t \) errors if and only if \( d \geq 2t + 1 \).
</div>


Assume a codeword \( x \in C \) is transmitted, and during transmission, at most \( t \) symbols are corrupted, resulting in a received word \( r \in \Sigma^n \). That is,
\[
d(x, r) \leq t.
\]
To decode correctly, the receiver must identify the original codeword \( x \) from \( r \). A standard decoding strategy is to choose the codeword \( y \in C \) that minimizes the Hamming distance \( d(r, y) \). For this strategy to work reliably, we want \( x \) to be the unique codeword within distance \( t \) of \( r \).


**(Only if direction)**
Suppose \( C \) can correct up to \( t \) errors. Then for any two distinct codewords \( x, y \in C \), the decoding balls of radius \( t \) around them must be disjoint:
\[
B_t(x) \cap B_t(y) = \emptyset.
\]
Otherwise, if \( r \in B_t(x) \cap B_t(y) \), then both \( d(x, r) \leq t \) and \( d(y, r) \leq t \), so \( r \) could be decoded ambiguously.

Now, by the triangle inequality for the Hamming distance:
\[
d(x, y) \leq d(x, r) + d(r, y) \leq t + t = 2t,
\]
which would contradict the assumption that the minimum distance of the code is \( d \). Therefore, to avoid such ambiguity, we must have:
\[
d(x, y) > 2t \quad \text{for all } x \neq y \in C.
\]
Hence, \( d \geq 2t + 1 \).


**(If direction)**
Now suppose the minimum distance \( d \geq 2t + 1 \). Let \( x \in C \) be the transmitted codeword and \( r \in \Sigma^n \) the received word with \( d(x, r) \leq t \). We claim that \( x \) is the unique codeword within distance \( t \) of \( r \).

Suppose for contradiction that there exists another codeword \( y \in C \), \( y \neq x \), such that \( d(y, r) \leq t \). Then:
\[
d(x, y) \leq d(x, r) + d(r, y) \leq t + t = 2t,
\]
which contradicts the assumption that \( d(x, y) \geq d \geq 2t + 1 \). Therefore, such a \( y \) cannot exist.

Hence, for every received word within distance \( t \) of a codeword \( x \), that codeword is uniquely closest, and the code can correct up to \( t \) errors. 

# Some bounds

Suppose Alice sends a codeword $x$, and during transmission, it gets corrupted and Bob receives a word $y$. Given that at most $t$ symbols were altered in the channel, we want to show that Bob can still correctly recover the original message.

Since Bob knows that at most $t$ errors could have occurred, he considers all codewords within Hamming distance $t$ of the received word $y$.\footnote{This is often visualized as placing a Hamming ball of radius $t$ around $y$.} Clearly, the original codeword $x$ lies within this ball, since $d(x, y) \leq t$.

Now, if $x$ is the only codeword within this ball, then Bob can unambiguously conclude that Alice must have sent $x$.

We claim that this is indeed the case, provided the code has minimum distance at least $2t + 1$. Suppose, for contradiction, there exists another codeword $x' \neq x$ such that $d(x', y) \leq t$. Then by the triangle inequality:
\[
d(x, x') \leq d(x, y) + d(y, x') \leq t + t = 2t,
\]
which contradicts the assumption that the minimum distance between any two codewords is at least $2t + 1$.

In other words, to move from one valid codeword to another through corruption, at least $2t + 1$ symbol changes are necessary. So if only $t$ symbols are corrupted, the received word is guaranteed to be closer (in Hamming distance) to the original codeword than to any other.


However, in practice, it may not be efficient to check all codewords within distance $t$ of $y$ to perform decoding. In fact, even determining whether a given string is a codeword may itself be computationally difficult.

This highlights two crucial properties we want from our codes in addition to large minimum distance:
- **Efficient codeword detection**: There should be an efficient way to verify whether a given string is a valid codeword.
- **Efficient decoding**: Given a corrupted word (close to some codeword), we should be able to efficiently recover the original codeword.


# Example: Repetition Code

Let us consider a simple code over the binary alphabet $\Sigma = \{0,1\}$. Define the repetition code of length $n = 3$ as:
\[
\mathcal{C} = \{000, 111\}
\]
This code encodes the bit $0$ as $000$ and $1$ as $111$. It is a $(3,1)$ block code: each message bit is encoded as a 3-bit codeword.

# Distance of the Code

The Hamming distance between the two codewords is:
\[
d(000, 111) = 3
\]
Hence, the minimum distance of the code is $d = 3$. Therefore:

- It can detect up to $d-1 = 2$ errors.
- It can correct up to $\left\lfloor \frac{d-1}{2} \right\rfloor = 1$ error.


# Error Correction Example 

Suppose Alice wants to send the bit $1$, so she transmits the codeword $111$.

**Case 1**: No error.  
Bob receives $111$, which is a valid codeword, and decodes it as $1$.

**Case 2**: One-bit error. 
Suppose the second bit is flipped: $111 \to 101$. Bob receives $101$. Now he checks distances:
\[
d(101, 000) = 2,\quad d(101, 111) = 1
\]
Bob decodes it as $111 \Rightarrow 1$. \textbf{Correctly decoded.}

**Case 3**: Two-bit error.}  
Suppose $111 \to 001$. Now:
\[
d(001, 000) = 1,\quad d(001, 111) = 2
\]
Bob decodes it as $000 \Rightarrow 0$. \textbf{Incorrect decoding.}

However, since $001 \notin \mathcal{C}$, Bob can at least detect that an error has occurred.
