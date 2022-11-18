---
layout: post
title:  "Differential Geometry"
date:   2021-11-04 18:39:45 -0500
categories: mathematics
---

[Cark Friedrich Gauss](https://en.wikipedia.org/wiki/Carl_Friedrich_Gauss), a cartographer, is the founding father of differential geometry. He developed many concepts (chart, atlas, map, coordinate system, geodesic, etc.) that are still used in mordern differential geometry.
The question that led to his famous Theorema Egreguim is whether we can draw an accurate map of a portion of our planet. The length of a curve $\lambda(t)$ for $t\in[a,b]$ on the surface of the globe is calculated by 

$$L(\lambda)=\int_a^b|\dot\lambda (t)|dt$$

By an accurate map, we mean a map $\phi:S^2\rightarrow \mathbb R^2$ from the globe $S^2$ to a plane $\mathbb R^2$ such that $L(\lambda)=L(\phi\circ\lambda)$. The answer is no. It is also impossible to draw an accurate map on the two dimensional plane for the minimum distance, called geodesic distance, between two points on the globe.

# Calculus in Euclidean Spaces
The differetiation and integration are well defined in Euclidean space (i.e., $\mathbb R^n$ equipped with inner product). Two important observations for differentiation in Euclidean spaces. First is linearity, that is, the change in $y=f(x)$ is a linear function of the change in $x$. Second is the chain rule, i.e., $d(g\circ f)=dg\circ df$, i.e., $dg(f(t))=\frac{dg}{df}\frac{df}{dt}$. The chain rule indicates that the derivative $\frac{dg}{df}$ is a linear map $\frac{dg}{df}: \frac{df}{dt}\mapsto \frac{dg}{dt}$, which can be used to define the derivative of a function with respect to a curve.

## A single variable real valued function
Consider two functions $y_1=x^2$ and $y_2 =2x^2$ (Figure 1). The derivative of $y_1$ is $\frac{dy_1}{dx}=2x$ and the derivative of $y_2$ is $\frac{dy_2}{dx}=4x$. Thus, $\frac{dy_2}{dy_1}=2: 2x\mapsto 4x$. The derivative with respect to a curve is a linear mapping of a tangent vector $\frac{dy_1}{dx}=2x$ to another tangent vector $\frac{dy_2}{dx}=4x$

[[figure_curve.png]]
Figure 1: The derivative of a function with respect to a curve. The black curve is $y_2=2x^2$ and the red curve is $y_1=x^2$. The black line is the tangent line of $y_2$ at $x=6$, while the red line is the tangent line of $y_1$ at $x=6$. The derivative of $y_2$ with respect to $y_1$ is 2

## Multivariate real valued functions

The chain rule for multivariate functions indicates that the derivative $D_\gamma f(\gamma(p))$ of a function $f:\mathbb R^m\rightarrow \mathbb R^n$ at a point $p\in\mathbb R$ with respect to a curve $\gamma:\mathbb R\rightarrow \mathbb R^m$ is a directional derivative of $f$ along the direction of the tangent vector of $\gamma$ at $p$, i.e., $D_\gamma f(\gamma(p))=D_{T_{\gamma(p)}\gamma} f$, where $T_{\gamma(p)}\gamma$ is the tangent vector of $\gamma$ at point $\gamma(p)\in \mathbb R^m$. The derivatie is a linear map is given by $$D_\gamma f(\gamma(p))=J_{n\times m}: T_{\gamma(p)}\mathbb R^m\rightarrow T_{f(\gamma(p))}\mathbb R^n$$

where $J_{m\times n}$ is the Jacobin matrix. Let $g:\mathbb R^k\rightarrow \mathbb R^m$ be a function and $f:Im(g)\subset\mathbb R^m \rightarrow \mathbb R^n$. The derivative $D_gf(p)$ of the function $f$ at a point $p\in \mathbb R^k$ with respect to the function $g$ is a linear map $$D_gf(g(p))=J_{n\times m}: T_{g(p)}\mathbb R^m\rightarrow T_{f(g(p))}\mathbb R^n$$

The derivative of $f$ with respect to $g$ at point $p$ is a linear map from the tangent space of $g$ at point $g(p)$ to the tangent space of $f$ at point $f(g(p))$. We have omitted the technical details necessary for the above conclusion. The conclusion that the derivative between two functions is a linear map between two tangent vector spaces can be used to define the derivatives on differential manifold.

# Topological Manifold

## Set theory
<iframe width="560" height="315" src="https://www.youtube.com/embed/6EIWRg-6ftQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Topological space
<iframe width="560" height="315" src="https://www.youtube.com/embed/6EIWRg-6ftQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Topological manifold
A **topological manifold** is a topological space which is locally homeomorphic to a Euclidean space. Each point in the manifold is equipped with a local coordinate system, which is constructed through a **chart**, i.e., a local **homeomorphic** to a Euclidean space. The **dimension** of the topolocal manifold is equal to the dimension of the locally homeomorphic Euclidean space. The topology of a topological manifold can be inherited by any subset of the manifold. **Submanifold** can be constructed through the relative topology inherited from the manifold.

A topological manifold provides a local structure necessary for continuous maps to work on a geometric object. However, it requires additional structure to allow differentiation and integration on the manifold. A **smooth manifold** is a topological manifold which is locally **diffeomorphic** to a Euclidean space. Differentiation at a point in the smooth manifold is constructed on the **tangent space**, in which a tangent vector is the velocity of a smooth curve in the manifold. **Derivatives** are defined through charts similarly as those defined in the Euclidean spaces. To perform vector calculus on the manifold, a **vector field**, **integral curves**, and **flow of a vector field** are defined. A vector field of a manifold can be mapped to another vector field of another manifold or vice versa through two linear maps **pullback** and **pushforward**. The differential of a vector field is defined through **Lie bracket**. A more general defination **derivation** of a vector field is given in the context of the **Lie algebra** of a **Lie group**.

A smooth manifold is represented by a set of local coordinates. Reconstruction of the global geometric object from local coordinates is possible for a smooth manifold with a **Hausdorff topology**, i.e., Riemanian metric manifold. The existance of a coutable atlas indicates that a smooth manifold with a Hausdorff and second coutable topology is **metrizable** and **paracompact**.

<iframe width="560" height="315" src="https://www.youtube.com/embed/uGEV0Wk0eIk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### Chart
Let $U\subset M$ be a subset of a manifold M. A chart is a pair $(U,\psi)$ where $\psi: U\rightarrow \mathbb{R}^k$ is a bijection map from $U$ to an open set $\psi(U)\subset \mathbb{R}^k$.

A atlas is a collection of charts $\mathscr A=\{(\psi_\alpha,U_\alpha)\}_{\alpha\in A}$ that cover the manifold M.

# Differentiable manifold
<iframe width="560" height="315" src="https://www.youtube.com/embed/Fa6SRAwY80Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Tangent space

## Differentiable functions on a manifold
A real valued function $f:M\rightarrow R$ on a $n$ dimensional differentiable manifold $M$ is said to be differentiable at a point $p\in M$ if it is differentiable in any coordinate chart around $p$. Specifically, if $(U,\phi)$ is a differentiable chart where $U$ is an open set in $M$ containing $p$, then $f$ is differentiable if and only if $f\circ \phi^{-1}: \phi(U)\rightarrow \mathbb R$ is differentiable at $\phi (p)$.
### Equivalent curves
Two curves $\gamma_1$ and $\gamma_2$ with $\gamma_1 (0)=\gamma_2(0)=p$ in a differentiable manifold $M$ are equivalent, denoted by $\gamma_1 \equiv \gamma_2$, if for any coordinate chart $\phi$,
$$\frac{d}{dt}\phi\circ \gamma_1(t)|_{t=0}=\frac{d}{dt}\phi\circ \gamma_2(t)|_{t=0}$$
The equivalence classes are curves through *p* with a prescribed [velocity vector](https://en.wikipedia.org/wiki/Velocity_vector "Velocity vector") at *p*.

### Tangent space
A tangent vector at a point $p\in M$ is an equivalent class of differentiable curves $\gamma$ with $\gamma(0)=p\in M$.  The collection of all tangent vectors at *p* forms a [vector space](https://en.wikipedia.org/wiki/Vector_space "Vector space"): the [tangent space](https://en.wikipedia.org/wiki/Tangent_space "Tangent space") to $M$ at $p$, denoted $\color{red}T_pM$.

##### A tangent vector for embedded manifold

Let $M\subset R^k$ be a smooth m-dimensional manifold and a point $p\in M$. A tangent vector is defined as a vector $v\in R^k$ such that $v=\dot{\lambda}(0)$ for a smooth curve $\lambda$ with $\lambda(0)=p$. Let $\phi_0:U_0\rightarrow \Omega_0$ be a diffeomorphism onto an open subset $\Omega_0 \subset R^m$. Let $x_0=\phi_0(p)$ and $\psi_0=\phi_0^{-1}$. We want to show that $$Im\big(d\psi_0(x_0):R^m\rightarrow R^k\big)\subset T_pM$$Let $\gamma(t)=\psi_0(x_0+t\sigma)$ where $\sigma\in R^m$. Then $\gamma$ is a smooth curve in M satisfying $\gamma(0)=p$ and $\dot{\gamma}(0)=d\psi_0(x_0)\sigma$.

### Directional derivative

Let $\gamma(t)$ be a differentiable curve in a $n$ dimensional differentiable manifold $M$ with $\gamma(0)=p$. The directional derivative of $f$ at point $p$ along the curve is $\frac{d}{dt}f(\gamma(t))|_{t=0}$.
By the chain rule, $\frac{d}{dt}f(\gamma(t))=\frac{d}{dt}(f\circ \phi^{-1}\circ \phi \circ \gamma(t))$, the function $f$ has the same directional derivative at *p* along two equivalent curves $\gamma_1$ and $\gamma_2$. Thus, the directional derivative depends only on the [tangent vector](https://en.wikipedia.org/wiki/Tangent_vector "Tangent vector") of the curve at *p*.

### The differential
Let $X$ be a tangent vector at $p\in M$ and $f$ is a differentiable function. Define the derivative of $f$ at $p$ along the tangent vector as $Xf(p):=\frac{d}{dt}f(\gamma(t))|_{t=0}$. If $f$ is fixed, then the map $X\mapsto Xf(p)$ is a linear functional on the tangent space. This linear functional is denoted by $\color{red}df(p)$ and is called the differential of $f$ at $p$, i.e., $df(p):T_pM\rightarrow \mathbb R$.

Def: Let $M\subset \mathbb{R}^n$ be a smooth $m$-dimensional manifold and a point $p\in M$. A vector $v\in \mathbb{R}^n$ is a tangent vector of $M$ at $p$ if there exists a smooth curve $\gamma:R\rightarrow M$ such that $\gamma(0)=p$ and $\dot{\gamma}(0)=v$.  
The set $T_pM := \{\dot{\gamma}(0)|\gamma:R\rightarrow M, \gamma(0)=p\}$ of tangent vectors of $M$ at $p$ is called the tangent space of M at p.
## Derivative
Def: Let $f:M\rightarrow \mathbb{R}^k$ be a smooth function. The derivative of $f$ at a point $p\in M$, denoted by $df(p)$, is a linear function $df(p):T_pM\rightarrow\mathbb{R}^k$, defined by $df(p)v:=\frac{df(\gamma(t))}{dt}=\lim_{h\rightarrow0}\frac{f(\gamma(h))-f(p)}{h}$, where $\gamma:R\rightarrow M$ is a smooth curve satisfying $\gamma(0)=p$ and $\dot{\gamma}(0)=v$.
This is the directional derivative of $f$ in the direction of $v$, i.e., the change of $f$ along the smooth curve $\gamma$.
## Diffeomorphism
Thereom: Let $M ⊂ R^k$ be a smooth $m$-manifold and $N ⊂ R$ be a smooth $n$-manifold and let $f : M → N$ be a diffeomorphism. Then $m = n$ and the differential $df(p): T_pM → T_{f(p)}N$ is a vector space isomorphism with inverse $df(p)^{− 1} = df^{−1}(f(p)):T_{f ( p )}N → T_pM$ for all $p ∈ M$.
## Inverse function theorem
Let $M ⊂ R^k$ and $N ⊂ R^l$ be smooth $n$-manifolds and $f : M → N$ be a smooth map. Let $p_0 ∈ M$ and suppose that the differential $df ( p_0 ) : T_{p_0}M →T_{f(p_0)}N$ is a vector space isomorphism. Then there is an $M$-open neighborhood $U ⊂ M$ of $p_0$ such that $V := f ( U ) ⊂ N$ is an $N$-open subset of $N$ and the restriction $f |_U : U → V$ is a diffeomorphism.

<iframe width="560" height="315" src="https://www.youtube.com/embed/4l-qzZOZt50" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
</iframe>

# Tensor fields

<iframe width="560" height="315" src="https://www.youtube.com/embed/V0TPgeiyWCo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
</iframe>

# Grassmann algebra

# Lie groups and Lie algebras

# Fibre bundles

# Connection 1-form

# Parallel transport

# Curvature

# Covariant derivatives
