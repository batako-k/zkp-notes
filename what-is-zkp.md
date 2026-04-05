# zkp-notes
My study notes on Zero-Knowledge Proofs

## Topics
- What is ZKP
- Add topics section

# Zero-Knowledge Proof (ZKP)

## 1. Completeness（完全性）

もし $x \in L$ なら、正しい証明者 $P$ に対して検証者 $V$ は受理する：

$$
x \in L \Rightarrow \Pr[V \ accepts] \approx 1
$$

---

## 2. Soundness（健全性）

もし $x \notin L$ なら、不正な証明者はほぼ騙せない：

$$
x \notin L \Rightarrow \Pr[V \ accepts] \approx 0
$$

---

## 3. Zero-Knowledge（ゼロ知識性）

検証者が見る情報は、シミュレーターでも生成できる：

$$
View_V(P(x, w)) \approx S(x)
$$

---

## 離散対数型 ZKP（例）

公開情報：

$$
y = g^x
$$

### プロトコル

1. ランダム値を選ぶ  
$$
r \in \mathbb{Z}
$$

2. コミットメントを計算  
$$
t = g^r
$$

3. チャレンジ（ランダム）  
$$
c \leftarrow \text{random}
$$

4. 応答を計算  
$$
s = r + cx
$$

5. 検証  
$$
g^s = t \cdot y^c
$$

---

## 検証の意味（式変形）

$$
g^s = g^{r + cx}
$$

$$
= g^r \cdot (g^x)^c
$$

$$
= t \cdot y^c
$$
