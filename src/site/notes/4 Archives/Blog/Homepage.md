---
{"dg-publish":true,"dg-path":"QuickStart/Homepage.md","permalink":"/QuickStart/Homepage/","pinned":true,"tags":["gardenEntry"],"noteIcon":"","created":"2024-07-25T12:14:39.204+08:00","updated":"2024-07-26T10:48:57.000+08:00"}
---

# LiQ's Blog

## Basic Idea
$$\begin{align}\text{Min }\;&\mathbf{c}^T\mathbf{x} \\
\text{(LP)}\quad\quad\text{s.t. }\;&\mathbf{Ax=b} \\
&\mathbf{x\ge 0}
\end{align}$$
- (Resolution Theorem) 如果可行域是非空，那么至少有一个顶点（极点） 
- (==Fundamental Theorem==) 如果可行域非空，并且目标值 $z$ 非 unbounded，则至少有一个顶点（极点）达到最优
- 可行域（多面体）有有限个数顶点（极点） $C_n^m$
- 顶点可以以 bfs. 的形式代数生成
> 如果 $C_n^m$ 足够小，可通过穷举顶点的方式找到最优解
> 当 $C_n^m$ 很大，需要一个 systematic and efficient 方式求解——单纯形法

![|500](/img/user/PHOTO/单纯形法-1.png)
#### Optimality Conditions
@ [Preliminary#寻找Basic sol](Preliminary.md#How%20to%20find%20basic%20solution?) 
$$\begin{align}\text{(indices of basic variables) }\;&B(1),\ldots,B(m) \\
\text{(basis matrix) }&\mathbf{B}=[\mathbf{A}_{B(1)},\ldots,\mathbf{A}_{B(m)}] \\
&x_\mathbf{B}=(x_{B(1)},\ldots,x_{B(m)})=\mathbf{B}^{-1}\mathbf{b}
\end{align}$$
- feasible direction : 使 $\mathbf{x}+\theta\mathbf{d}\in P\;,\theta>0$ 的向量 $\mathbf{d}$
$$\begin{align}
\mathbf{A}(\mathbf{x}+\theta\mathbf{d})&=\mathbf{b}\\&\Downarrow\\ \mathbf{Ad}&=\mathbf{0} \\
&\Downarrow\text{(let }d_j=1,d_i=0\text{ for other nonbasic variables)}  \\ 
\mathbf{0=Ad}&=\mathbf{Bd_B+A}_j \\ 
&\Downarrow  \\
\text{(j-th basic direciton) }\;\mathbf{d_B}&=-\mathbf{B}^{-1}\mathbf{A}_j \\
&\Downarrow  \\
(\text{cost change along }\mathbf{d})\;\;r_j&=\mathbf{c}^T \mathbf{d}=\mathbf{c_B}^T \mathbf{d_B }+c_j=c_j-\mathbf{c_B}^T\mathbf{B}^{-1}\mathbf{A}_j\end{align}$$ 
- reduced cost : $r_j=c_j-\mathbf{c_B}^T\mathbf{B}^{-1}\mathbf{A}_j$
> [!EXAMPLE]
![|650](https://liq-keep.oss-cn-qingdao.aliyuncs.com/img1/%E5%8D%95%E7%BA%AF%E5%BD%A2%E6%B3%95-2.png)

> [!TIP]+ Optimal Conditions (Theorem 3.1)
> Consider bfs. $\mathbf{x}$ associated with basis matrix $\mathbf{B}$ ,reduced cost $\mathbf{r}$
> - If $\mathbf{r}\ge\mathbf{0}$ ,then $\mathbf{x}$ is optimal.
> - If $\mathbf{x}$ is optimal and nondegenerate ,then $\mathbf{r}\ge\mathbf{0}$

> *定理从例子较为直观，证明略*
> 由此，只要能够类似上述例子中找到 reduced cost ，即可找到更好的 bfs. ，也可依此判断当前（Step2）是否最优。

#### Degenerate Situation？


## Simplex Method
<div><ul class="dataview list-view-ul"><li><span>Fundamental Theorem</span></li></ul></div>

## How to find a feasible solution?
