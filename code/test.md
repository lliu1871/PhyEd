---
layout: markdown
title: test
permalink: /code/test
author: "Liang Liu"
output: html_document
date: 2021-04-16
---

Hello, $x+1$. here is an equation \\(\alpha\\)

$$\int_i f(x)dx = \sigma+\beta$$

# Introduction
<iframe width="560" height="315" src="https://www.youtube.com/embed/TrcCbdWwCBc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
# Representing points in $\mathbb{R}^n$
# Transformations
# Partial derivative

## Definition
Let $f:V\rightarrow \mathbb{R}$  be a scalar mapping from a vector space $V$ to $\mathbb R$. Let $h\in \mathbb R$ be a scalar and $v\in V$ is a vector in $V$. The directional derivative of $f$ gives the change of $f$ per unit of distance moved in the direction given by the vector $v$, which is 

$$\nabla_vf(x)=\lim_{h\rightarrow 0} \frac{f(x+hv)-f(x)}{h}$$

This definition is valid even when the norm of a vector is undefined. If $f$ is differentiable, then the directional derivative exists along any vector $v$ at $x$, and 

$$\nabla_vf(x)=\nabla f(x)\cdot v$$

## Properties
- sum rule: $\nabla_v(f+g)=\nabla_vf+\nabla_vg$ 
- constant factor rule: $\nabla_v(cf)=c\nabla_vf$
- product rule: $\nabla_v(fg)=g\nabla_vf+f\nabla_vg$
- chain rule: $\nabla_v(f\circ g)=\nabla_{g(v)}f \circ \nabla_vg$

# Differential of vector valued function
