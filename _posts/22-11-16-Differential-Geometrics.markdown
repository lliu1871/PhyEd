--
layout: post
---

# History
[Cark Friedrich Gauss](https://en.wikipedia.org/wiki/Carl_Friedrich_Gauss), a cartographer, is the founding father of differential geometry. He developed many concepts (chart, atlas, map, coordinate system, geodesic, etc.) that are still used in mordern differential geometry. 
The question that led to his famous Theorema Egreguim is whether we can draw an accurate map of a portion of our planet. The length of a curve $\lambda(t)$ for $t\in[a,b]$ on the surface of the globe is calculated by $L(\lambda)=\int_a^b|\dot\lambda (t)|dt$. By an accurate map, we mean a map $\phi:S^2\rightarrow \mathbb R^2$ from the globe $S^2$ to a plane $\mathbb R^2$ such that $L(\lambda)=L(\phi\circ\lambda)$. The answer is no. It is also impossible to draw an accurate map on the two dimensional plane for the minimum distance, called geodesic distance, between two points on the globe. 
# Calculus in Euclidean Spaces
The differetiation and integration are well defined in Euclidean space (i.e., $\mathbb R^n$ equipped with inner product). Two important observations for differentiation in Euclidean spaces. First is linearity, that is, the change in $y=f(x)$ is a linear function of the change in $x$. Second is the chain rule, i.e., $d(g\circ f)=dg\circ df$, i.e., $dg(f(t))=\frac{dg}{df}\frac{df}{dt}$. The chain rule indicates that the derivative $\frac{dg}{df}$ is a linear map $\frac{dg}{df}: \frac{df}{dt}\mapsto \frac{dg}{dt}$, which can be used to define the derivative of a function with respect to a curve.
## A single variable real valued function
Consider two functions $y_1=x^2$ and $y_2 =2x^2$ (Figure 1). The derivative of $y_1$ is $\frac{dy_1}{dx}=2x$ and the derivative of $y_2$ is $\frac{dy_2}{dx}=4x$. Thus, $\frac{dy_2}{dy_1}=2: 2x\mapsto 4x$. The derivative with respect to a curve is a linear mapping of a tangent vector $\frac{dy_1}{dx}=2x$ to another tangent vector $\frac{dy_2}{dx}=4x$
![[figure_curve.png]]
Figure 1: The derivative of a function with respect to a curve. The black curve is $y_2=2x^2$ and the red curve is $y_1=x^2$. The black line is the tangent line of $y_2$ at $x=6$, while the red line is the tangent line of $y_1$ at $x=6$. The derivative of $y_2$ with respect to $y_1$ is 2
