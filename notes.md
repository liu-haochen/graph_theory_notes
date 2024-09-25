Proposition 1.3.1.

pf:令$x_0 ,\cdots,x_n$是图$G$一条最长路径，因此$x_n$一定只与$x_0\cdots x_{n-1}$相邻，因此$\delta(x_n)\le d(G) \le |\{x_0,\cdots,x_{n-1}\}|=n$.从而该路径的长度一定大于等于$\delta(G)$.

对于上述的路径,令$i = \min_i \{x_i与x_n相邻\}$,则环$x_i \cdots x_n x_i$是长至少为$\delta(G)+1$的circle.

---
Proposition 1.3.2.

pf:令$x_0 \cdots x_n x_0$是一个图$G$中长度最小的circle $C^{n+1}$,则显然这个circle是无chord的,因此其中的任意两个点都不会被除了该circle内的其他路径连接.

若$n+1$为奇数,则$\frac{n}{2}=d(x_0,x_{\frac{n}{2}})\le {\rm diam(G)}$,因此$n+1\le 2{\rm diam(G)}+1$

若$n+1$为偶数,则$\frac{n+1}{2} = d(x_0,x_{\frac{n+1}{2}}) \le {\rm diam(G)}$,从而$n+1\le 2{\rm diam(G)} \le {\rm diam(G)}+1$

---

As one easily checks: $\rm rad(G)\le diam(G) \le 2rad(G)$

pf:$\exist x,y \in V(G)$ s.t. $ \rm rad(G) = d(x,y) \le diam(G)$.


令$s,t$为$\rm d(s,t)=diam(G)$,$r$为中心，则$\rm diam(G)=d(s,t)\le d(s,r)+d(r,t)\le 2rad(G)$

---

Proposition 1.3.3.

pf:令$G$的中心为$c$,则$V(G)$可以按离$c$的距离被划分为$V(G) = \cup_{i=0}^k V_i$,其中$V_i = \{v|v\in V(G),d(c,v) = i\}.$

注意到$|V_0|=1$,$|V_1|\le d$,而$|V_{i+1}| \le (d-1)|V_i| $,这是因为$V_{i+1}$的每个点都是由某个$V_i$的点相邻而来的,并且$V_i$除掉与$V_{i-1}$有一个相邻点后至多还剩下$d-1$个相邻点.

因此$|V_{i+1}| \le (d-1)^i d$,从而$|V(G)| =1 + d + (d-1) d + (d-1)^2 d + \cdots + (d-1)^{k-1}d = 1+d\frac{1-(d-1)^k}{1-(d-1)} \le \frac{d}{d-2} (d-1)^k$

---

Proposition 1.4.1. 一个连通图G一定可以找到一列点$v_0,\cdots v_n$使得所有
$$
G_i = G[v_0,\cdots ,v_i]
$$
都是连通的.

Therorem 1.5.1. 下面四个对于图T的命题等价:

(i)T是tree

(ii)在T中任何两个点都有唯一的路径

(iii)T是极小的连通图,即T连通但对任意$e\in E(T)$ , $T-e$就不连通了.

(iv)T是极大的无cycle图,即T不包含cycle但是对任何$x,y\in V(T)$,若$xy\not \in E(T)$,则$T+xy$都存在cycle

pf:(i)$\implies$(ii)

由于$T$连通，存在路径是显然的，只证明唯一性。取$x,y\in T$,假设有两条路径$x,z_0\cdots z_n y$以及$x,t_0\cdots t_l y$.取$k=\min_i z_i\not=t_i$,则$\{z_{k+1},\cdots,z_n,y\}\cap \{t_{k+1},\cdots,t_n,y\} \not= \emptyset$.同样取最小的那个$z_j=t_m$,则$G$中存在cycle $z_k z_{k+1}\cdots z_j t_{m-1}\cdots t_k $,这与$T$是tree矛盾.

(ii)$\implies$(iii)

令$e=xy$则$x,y$的唯一路径为$e$,$T-e$后就不存在路径连接$x,y$,因此$T-e$不连通.

(iii)$\implies$(iv)

若$T$有cycle,则令cycle为$x_0\cdots x_n x_0$,令$e=x_n x_0$,$T-e$仍然连通,这与(iii)矛盾.因此$T$不存在cycle.$T$连通,因此存在路径$xTy$,因此$T+xy$有cycle $xTyx$.

---

Corollary 1.5.3. 有$n$个顶点的连通图$G$是tree等价于这个图的边个数是$n-1$

pf:若$G$是tree,则由推论1.5.2,令$\{v_1,\cdots v_n\}$ 满足 $G_i := G[v_1,\cdots,v_i]$连通,且每个$v_i$只与$v_1,\cdots,v_{i-1}$中一个相邻.从而有$|E(G_0)|=0,|E(G_k)|=|E(G_{k-1})|+1$,因此$|E(G)|=|E(G_n)|=n-1$.

反过来若$|E(G)|=n-1$,我们说明$G$是极小的连通图.同样令$\{v_1,\cdots v_n\}$ 满足 $G_i := G[v_1,\cdots,v_i]$连通.此时每个$v_i$至少与$v_1,\cdots,v_{i-1}$中一个相邻,因此$|E(G_0)|=0,|E(G_k)|\ge|E(G_{k-1})|+1$,即$|E(G)|=|E(G_n)|\ge n-1$.从而只有$n-1$条边的图是极小的连通图.

---

Corollary 1.5.4. 令$T$是一个tree,$G$是任意满足$\delta(G)\ge |T|-1$,则$T$可以视作$G$的子图.

对$n=|T|$用强归纳法.

当$n=2$命题显然成立,只要任取$G$的一条边$e=xy$即可.

假设当 $n<m$ 都成立现在证明$n=m$时成立.同样假设$v_1,\cdots v_m \in V(T)$为满足$T_i = T[v_1,\cdots v_i]$连通的 $\{v_i\}$,由归纳假设可知$T_{m-1}$可以通过映射$f$嵌入到$G$中,由命题假设有$d_G(f(v_{m-1})) \ge |T|-1$,因而$N_G(f(v_{m-1}))\backslash T_{m-1} \not= \emptyset $,取$g\in N_G(f(v_{m-1}))\backslash T_{m-1} $,令$f$扩张到$\hat{f}:T\to G$为
$$
\hat{f}(v)=\left\{
\begin{array}{cc}
g & v=v_m \\
f(v)&\text{else}
\end{array}\right.
$$

---

Lemma 1.5.5. 令$T$是一个$G$中的normal tree.

(i)任何2点$x,y\in T$ 在$G$中是被$\lceil x \rceil \cap \lceil y \rceil $ seperated .

(ii)

pf:(i)若存在$T$-path的终点恰好是$x,y$.则由定义x,y在$T$-order下是可比较的,不妨假设$x<_T y$,则 $\lceil x \rceil \cap \lceil y \rceil = \lceil x \rceil$.,显然$x,y$会被$\{x\}$ seperated.

