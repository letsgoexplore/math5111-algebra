# Cheat Sheet · MATH5111

只收定义、判定、例子、一句话定理。本课范围。

---

## Aut 与经典群

| 符号 | 定义 / 判定 | 例 |
| --- | --- | --- |
| \(\mathrm{Aut}\,X\) | \(X\) 的结构自同构全体，成群 | \(G=\mathrm{Aut}\,X\) 是板书默认语法 |
| \(GL(V)\) | \(V\to V\) 线性可逆映射 | \(V\) 为 \(k\)-线性空间 |
| \(GL_n(k)\) | 可逆 \(n\times n\) 矩阵 / \(k\) | \(GL_n(k)\cong GL(k^n)\) |
| 欧氏空间 | 实线性空间 + 内积 | \(\mathbb{R}^n\) + dot product |
| \(O(V)\) / \(O(n)\) | 保内积的线性自同构 | \(O(n)=\mathrm{Aut}(\mathbb{R}^n,\text{dot})\) |
| \(SO(n)\) | 再保 standard orientation | \(\det=1\) 的正交矩阵 |

\[
GL_n(\mathbb{R})\supset O(n)\supset SO(n)
\]

---

## 同态

**群** \(\varphi:G_1\to G_2\)

- 定义只需 \(\varphi(ab)=\varphi(a)\varphi(b)\)。
- \(\varphi(e)=e\)、\(\varphi(a^{-1})=\varphi(a)^{-1}\)：**冗余**。

**幺半群** \(\varphi:M_1\to M_2\)

- 必须同时：\(\varphi(ab)=\varphi(a)\varphi(b)\) **且** \(\varphi(e)=e\)。
- 保乘法 \(\not\Rightarrow\) 保单位。

**例（幺半群不是群）**

\[
(\mathbb{Z}/6\mathbb{Z},\times)^\times=\{\bar1,\bar5\}\cong\mathbb{Z}/2\mathbb{Z},
\qquad
\bar2\cdot\bar3=\bar0.
\]

---

## 群作用

**左作用** \(G\times X\to X\)，\((g,x)\mapsto g\cdot x\)

1. \(e\cdot x=x\)
2. \(g_1\cdot(g_2\cdot x)=(g_1g_2)\cdot x\)

**等价：** 群同态 \(\phi:G\to\mathrm{Aut}\,X\)，\(g\cdot x=\phi(g)(x)\)。

**右乘改左作用：** \((g,x)\mapsto xg^{-1}\)。

| 名词 | 符号 | 定义 |
| --- | --- | --- |
| 轨道 | \(G\cdot x\) | \(\{g\cdot x\mid g\in G\}\) |
| 稳定化子 | \(G_x\) | \(\{g\in G\mid g\cdot x=x\}\le G\) |
| 不动点 | — | \(G_x=G\) 的那些 \(x\) |

**划分：** 轨道两两不交，\(X=\coprod G\cdot x_\alpha\)。  
有限：\(|X|=\sum|G\cdot x_\alpha|\)。  
等价关系：\(x\sim y\Leftrightarrow \exists g,\; y=g\cdot x\)。

**纤维对照：** \(f:X\to Y\) 满射 \(\Rightarrow\{f^{-1}(y)\}\) 也是划分。

---

## \(G\) 作用在 \(G\)

| 动作 | 公式 | 立刻能用的结论 |
| --- | --- | --- |
| 左平移 | \(x\mapsto gx\) | \(G_x=\{e\}\)（自由） |
| 右平移 | 右作用 \(x\mapsto xg\)；左作用 \(x\mapsto xg^{-1}\) | 轨道是陪集 |
| 共轭 | \(\mathrm{Ad}_g x=gxg^{-1}\) | \(\mathrm{Ad}:G\to\mathrm{Aut}\,G\) 是同态；轨道 = **共轭类** |

共轭保运算（板书）：

\[
\mathrm{Ad}_g(xy)=gxyg^{-1}=(gxg^{-1})(gyg^{-1}).
\]

---

## 正规子群

\(H\le G\) 正规 \(H\trianglelefteq G\) \(\iff\) \(\forall g,\; gHg^{-1}=H\)（self-conjugate）。

- \(ghg^{-1}\) 仍在 \(H\)，但**可以 \(\neq h\)**。
- 等价常用说法：\(\forall g,\; gH=Hg\)。

---

## 陪集

\(H\) 左乘作用 \(H\times G\to G\)，\((h,g)\mapsto hg\)。

| | 写法 | 空间 |
| --- | --- | --- |
| 右陪集 | \(Hg=\{hg\}\) | \(H\backslash G\) |
| 左陪集 | \(gH=\{gh\}\) | \(G/H\) |

**集合同构（永远成立）：**

\[
Hg\cong H\cong gH,\qquad hg\leftarrow h\rightarrow gh.
\]

**子集相等 \(Hg=gH\)：** 不是永远成立；全体 \(g\) 都成立 \(\Leftrightarrow H\trianglelefteq G\)。

---

## 例：\(SO(2)\) 转平面

| 点 | \(G_x\) | 轨道 |
| --- | --- | --- |
| \(x\neq O\) | \(\{e\}\) | 圆 \(G\cdot x\)（板上标了 \(R(\pi/2)\cdot x\)、\(R(\pi)\cdot x\)） |
| 原点 \(O\) | \(SO(2)\) | \(\{O\}\) |

口诀：稳定化子越大，轨道越小。

---

## Lagrange

**定理。** \(H\le G\) 且 \(G\) 有限 \(\Rightarrow o(H)\mid o(G)\)。

**板书证明骨架。** \(H\) 平移作用在 \(G\) 上 → 轨道 = 陪集 → 每块 \(\cong H\) →

\[
|G|=\sum|H|=|H|\cdot|I|,\qquad |I|=[G:H].
\]

---

## Euler（Lagrange 特化）

设定：\(n>1\)，\(\gcd(a,n)=1\)。

\[
\varphi(n)=\lvert(\mathbb{Z}/n\mathbb{Z})^\times\rvert,
\qquad
a^{\varphi(n)}\equiv 1\pmod n.
\]

\((\mathbb{Z}/n\mathbb{Z})^\times\) 是幺半群 \((\mathbb{Z}/n\mathbb{Z},\times)\) 的单位群。

**例。** \((\mathbb{Z}/6\mathbb{Z})^\times=\{\bar1,\bar5\}\)，\(\varphi(6)=2\)，\(\bar5^2=\bar1\)。

---

## 30 秒口诀

1. 群 = \(\mathrm{Aut}\,X\)；结构加一档，群小一档。
2. 群同态一条乘法；幺半群必须再写单位。
3. 作用 \(\Leftrightarrow\) \(G\to\mathrm{Aut}\,X\)。
4. 左乘出右陪集 \(Hg\)；共轭轨道叫共轭类。
5. \(gHg^{-1}=H\) \(\Leftrightarrow\) 正规。
6. 轨道划分；陪集等大；有限则 Lagrange；单位群则 Euler。
