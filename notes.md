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

pf:令$\{v_1,\cdots v_n\}$ 满足 $G_i := G[v_1,\cdots,v_i]$连通.若$G$是tree,则