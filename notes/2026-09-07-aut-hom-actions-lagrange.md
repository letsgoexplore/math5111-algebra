# 2026-09-07 课堂笔记：自同构、同态、群作用与 Lagrange

> 来源：9 张白板。顺序按讲课推进整理，公式与记号尽量贴近板书。

| 板 | 主题 | 原图 |
| --- | --- | --- |
| 1 | \(G=\mathrm{Aut}\,X\)，经典线性群 | [01](figures/2026-09-07/01-aut-classical-groups.jpg) |
| 2–3 | 群同态 vs 幺半群同态 | [02](figures/2026-09-07/02-homomorphisms-overview.jpg) · [03](figures/2026-09-07/03-group-vs-monoid-hom.jpg) |
| 4 | 群作用 \(\Leftrightarrow\) 同态 \(G\to\mathrm{Aut}\,X\)；\(SO(2)\) | [04](figures/2026-09-07/04-group-action-so2.jpg) |
| 5 | \(G\) 作用在自身：平移与共轭 | [05](figures/2026-09-07/05-g-on-g-conjugation.jpg) |
| 6 | 正规子群、陪集、\(SO(2)\) 稳定化子 | [06](figures/2026-09-07/06-normal-cosets-so2.jpg) |
| 7 | 陪集集合同构；轨道划分 | [07](figures/2026-09-07/07-coset-iso-orbits.jpg) |
| 8–9 | 轨道分解、Lagrange、Euler | [08](figures/2026-09-07/08-orbit-decomp-lagrange.jpg) · [09](figures/2026-09-07/09-euler-partition-lagrange.jpg) |

---

## 1. 群是对象的对称：\(G=\mathrm{Aut}\,X\)

板书把群先写成**某个对象的自同构群**：

\[
G=\mathrm{Aut}\,X.
\]

### 例 1：线性空间

设 \(V\) 是域 \(k\) 上的线性空间。则

\[
GL(V)=\text{the group of symmetries of }V,
\]

\[
\mathrm{Aut}\,V=\{\,T:V\to V\mid T\text{ 是线性等价}\,\}.
\]

矩阵写法：

\[
GL_n(k)=\text{域 }k\text{ 上可逆 }n\times n\text{ 矩阵全体}.
\]

### 例 2：欧氏空间与正交群

**Euclidean vector space**：带内积的实线性空间。此时保结构的自同构不再是全部线性等价，而是保内积的那些：

\[
O(V)=\mathrm{Aut}\,V.
\]

坐标化：

| 群 | 板书定义 |
| --- | --- |
| \(O(n)\) | \(\mathrm{Aut}(\mathbb{R}^n,\text{dot product})\) |
| \(SO(n)\) | \(\mathrm{Aut}(\mathbb{R}^n,\text{dot product, standard orientation})\) |

要点：对象 \(X\) 带的结构越多，\(\mathrm{Aut}\,X\) 越小。

\[
GL_n(\mathbb{R})\;\supset\;O(n)\;\supset\;SO(n).
\]

---

## 2. 同态：保运算 vs 保单位

### 群同态

设 \(G_1,G_2\) 是群。集合映射 \(\varphi:G_1\to G_2\) 叫做 **group homomorphism**，若它保群结构。板书列出三条：

1. \(\varphi(ab)=\varphi(a)\varphi(b)\quad\forall a,b\in G_1\)
2. \(\varphi(e_{G_1})=e_{G_2}\)
3. \(\varphi(a^{-1})=(\varphi(a))^{-1}\)

板书把 (2)(3) 括起来，写 **redundant**：对群而言，

\[
\varphi(ab)=\varphi(a)\varphi(b)
\quad\Longleftrightarrow\quad
\text{(2) 与 (3) 自动成立}.
\]

### 幺半群同态

设 \(M_1,M_2\) 是 monoid。\(\varphi:M_1\to M_2\) 是 **monoid homomorphism** 当且仅当

1. \(\varphi(ab)=\varphi(a)\varphi(b)\quad\forall a,b\in M_1\)
2. \(\varphi(e_{M_1})=e_{M_2}\)

板书在 (1)\(\Leftrightarrow\)(2) 上打叉：对幺半群，**保乘法推不出保单位**，第二条必须单列。

| | 群 | 幺半群 |
| --- | --- | --- |
| 保乘法 | 必需 | 必需 |
| 保单位 | 多余（可由乘法推出） | **必需，单独写** |
| 保逆 | 多余（可由乘法推出） | 无逆可谈 |

---

## 3. 群作用 \(\Leftrightarrow\) 同态 \(G\to\mathrm{Aut}\,X\)

### 定义（左作用）

\(G\) 是群，\(X\) 是集合。**left action** 是映射

\[
G\times X\to X,\qquad (g,x)\mapsto g\cdot x,
\]

满足

1. \(e\cdot x=x\)
2. \(g_1\cdot(g_2\cdot x)=(g_1 g_2)\cdot x\)

### 等价刻画

作用 \(\iff\) 群同态

\[
\phi:G\to\mathrm{Aut}\,X,
\]

约定 \(\phi(g):X\to X\)，并令

\[
g\cdot x=\phi(g)(x).
\]

这把第 1 节的「群 = 对称」和第 2 节的「同态」焊在一起：作用就是把 \(G\) 实现成 \(X\) 上的对称。

### 把右乘改写成左作用

板书另写过一种左作用（用来消化右平移）：

\[
G\times X\to X,\qquad (g,x)\mapsto x g^{-1}.
\]

取逆是为了让结合律方向对上：\((g_1 g_2)\) 先作用应等于先 \(g_2\) 再 \(g_1\)。

### 例：\(G=SO(2)\) 转平面

圆心 \(O\)，圆周上一点 \(x\)，以及

\[
R(\pi/2)\cdot x,\qquad R(\pi)\cdot x.
\]

整圈标成轨道 \(G\cdot x\)。

| 点 | 稳定化子 | 轨道 |
| --- | --- | --- |
| 非原点 \(x\) | \(G_x=\{e\}\) | 过 \(x\) 的圆 |
| 原点 \(O\) | \(G_O=SO(2)\) | \(\{O\}\) |

几何直观：转非原点必须是恒等才不动；原点被所有旋转固定。

---

## 4. \(G\) 作用在自身上的三种标准动作

| # | 名称 | 映射 | 公式 |
| --- | --- | --- | --- |
| 1 | Left translation | \(G\times G\to G\) | \((g,x)\mapsto gx\) |
| 2 | Right translation | 板书写成 \((x,g)\mapsto xg\) | 作为**右作用**；要做成左作用则用 \(x\mapsto xg^{-1}\) |
| 3 | Conjugation | \(G\times G\to G\) | \((g,x)\mapsto gxg^{-1}=\mathrm{Ad}_g x\) |

左平移的稳定化子：\(G_x=\{e_G\}\)（自由作用）。

### 共轭是自同构，而且 \(\mathrm{Ad}\) 是同态

先把 \(G\) 只看成集合时，有映射 \(G\to\mathrm{Aut}\,G\)（集合层面）。再验证 \(\mathrm{Ad}_g\) 保运算：

\[
\mathrm{Ad}_g(xy)=g(xy)g^{-1}=(gxg^{-1})(gyg^{-1})=\mathrm{Ad}_g x\cdot\mathrm{Ad}_g y.
\]

于是得到**群同态**

\[
\mathrm{Ad}:G\to\mathrm{Aut}\,G.
\]

板书加下划线：

> the orbits of the conjugation action are called the **conjugation classes**
> （共轭类）

---

## 5. 正规子群 = 共轭不变的子群

设 \(H\le G\)。称 \(H\) 是 \(G\) 的 **normal subgroup**，记 \(H\trianglelefteq G\)，若 \(H\) 在任意 \(g\in G\) 的共轭下不变：

\[
gHg^{-1}=H,\qquad gHg^{-1}=\{\,ghg^{-1}\mid h\in H\,\}.
\]

板书也叫 **self-conjugate subgp**。旁注：\(ghg^{-1}\) **可以是 \(H\) 里的另一个元素**——不变的是集合 \(H\)，不是每个元素都被钉住。

---

## 6. 陪集 = \(H\) 平移作用的轨道

\(H\le G\)。\(G\) 在自身上的左/右平移，限制后得到 \(H\) 在 \(G\) 上的平移作用：

\[
H\times G\to G,\qquad (h,g)\mapsto hg.
\]

过点 \(g\) 的轨道 \(Hg\) 叫做 \(H\) 在 \(G\) 里的 **right coset**。

| 对象 | 记号 |
| --- | --- |
| 全部右陪集 | \(H\backslash G\) |
| 全部左陪集 | \(G/H=\{gH\mid g\in G\}\) |

### Fact 1：作为集合，陪集都和 \(H\) 一样大

\[
Hg\;\cong\;H\;\cong\;gH
\quad\text{（set isomorphism）}
\]

对应：

\[
hg\;\leftarrow\;h\;\rightarrow\;gh.
\]

左、右陪集一般不相等（那正是正规性要管的事），但**基数相同**。

---

## 7. 轨道给出划分；满射的纤维也给出划分

### 作用 \(\Rightarrow\) 等价关系 \(\Rightarrow\) 划分

> The orbits of a group action of \(G\) on \(X\) give us a partition of \(X\).
>
> \(X=\) the disjoint union of orbits.
>
> So an action of \(G\) on \(X\) defines an equivalence relation on \(X\).

等价关系：\(x\sim y\) 当且仅当存在 \(g\) 使 \(y=g\cdot x\)。

板书旁有置换例子 \((1)(2)(3)\)、\((1\,2)(3)\)，用来提示 \(\mathrm{Aut}\) 有限集就是对称群里的置换。

### 满射的纤维

> More example of equivalence relation on \(X\) (i.e. partition of \(X\)).

若 \(f:X\to Y\) 满射，则纤维族

\[
\{\,f^{-1}(y)\mid y\in Y\,\}
\]

是 \(X\) 的一个划分。轨道划分是同一模式：把「落到同一轨道」看成纤维。

---

## 8. 轨道分解公式

\(G\) 作用在 \(X\) 上，轨道代表元 \(x_\alpha\)，\(\alpha\in I\)。则

\[
X=\coprod_{\alpha\in I} G\cdot x_\alpha.
\]

有限时数个数：

\[
|X|<\infty\quad\Longrightarrow\quad
|X|=\sum_{\alpha\in I}|G\cdot x_\alpha|.
\]

---

## 9. Lagrange：有限子群的阶整除群的阶

把上一节用到 \(X=G\)、\(H\) 以平移作用在 \(G\) 上：轨道恰好是陪集，每个轨道与 \(H\) 等势，故

\[
o(G)=|G|=\sum_{\alpha\in I}|H|=|H|\cdot|I|.
\]

这里 \(|I|\) 是陪集个数（指数）。因此

\[
o(H)\mid o(G).
\]

板书框出 **A theorem of Lagrange**，并写白话：

> The order of a (finite) subgroup divides the order of the group.

---

## 10. 数论例子：\((\mathbb{Z}/n\mathbb{Z})^\times\) 与 Euler

设 \(a,n\) 正整数，\(n>1\)，且 \(\gcd(a,n)=1\)。

- Euler totient：\(\varphi(n)=\lvert(\mathbb{Z}/n\mathbb{Z})^\times\rvert\)
- \((\mathbb{Z}/n\mathbb{Z})^\times\subset(\mathbb{Z}/n\mathbb{Z},\times)\) 是幺半群里的单位群
- **Euler**：\(a^{\varphi(n)}\equiv 1\pmod n\)

这是 Lagrange 的直接应用：\(\bar a\) 落在有限群 \((\mathbb{Z}/n\mathbb{Z})^\times\) 里，阶整除 \(\varphi(n)\)，从而 \(\bar a^{\varphi(n)}=\bar 1\)。

### 具体计算：模 6

\[
(\mathbb{Z}/6\mathbb{Z},\times)^\times=\{\bar 1,\bar 5\}\cong\mathbb{Z}/2\mathbb{Z}.
\]

零因子（所以 \(\bar 2,\bar 3\) 不是单位）：

\[
\bar 2\cdot\bar 3=\bar 6=\bar 0.
\]

---

## 本课一条线

```
对象 X 的对称 Aut X
        ↓ 同态 = 保结构的映射（群比幺半群少写两条）
G → Aut X
        ↓ 这就是 G 在 X 上的作用
轨道划分 X
        ↓ H 平移作用在 G 上，轨道 = 陪集
每个陪集 ≅ H  （集合）
        ↓ 有限时数个数
Lagrange: |H| 整除 |G|
        ↓ 取 G = (Z/nZ)^×
Euler: a^{φ(n)} ≡ 1 (mod n)
```
