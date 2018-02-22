---
layout: post
title:  "高维度问题"
author: Hai Lan
date: 2018-02-22
categories: data
tags: [AI,R]
use_math: true
comments: false
---

当解释变量的数目$p$，大于或者近似于观测数据数目$n$，则出现了高维度问题。高维度问题最明显的挑战是最小二乘方法不适用。（不能得出唯一解）但是更为严重的是过拟合。因为大的$p$，提供了太多的复杂度，回归拟合的不再是重复验证的统计逻辑，而是一次次偶然的噪声。这往往使得拟合的训练集MSE以及$R^2$都特别的漂亮，但是检验集的MSE则几乎与其自身的variance相当（模型几乎没有解释力）。另外即便通过我们之前讨论的方法，比如变量选择法、lasso方法以及降低维度的方法能够获得具备一定解释能力的模型，我们在分析模型的时候，也还要注意，在高维问题时，共线性会显得特别的突出。它会使得单独的理解$\beta_i$变得没有意义。