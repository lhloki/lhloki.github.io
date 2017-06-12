---
layout: post
title:  "Two Risky Assets"
author: Hai Lan
date:   2017-04-27 11:25:38 +0800
categories: investment
tags: [投资,资产配置,R]
use_math: true
comments: true
---





Let's assume there are tow risky assets. Asset One's return is denoted as `$r$` with expectation `$\mu$` and variance `$\sigma^2$`. Asset Two is somehow related with Asset One, whose return is `$\beta r+ \epsilon$`, where `$\epsilon$` is independent of `$r$`. Lucky `$\beta$` and `$E(\epsilon)=\alpha,Var(\epsilon)=\sigma^2(\epsilon)$` are known. Suppose there exists a risk-free money account with determined return rate `$r_f$`.

# The Optimal Risky Portfolio
If all investors in the market are mean-variance investors, they should all invested in the same risky portfolio, which we call it "The One Fund", in turn, the market portfolio.
The consistence of the optimal risky portfolio has nothing to do with the risk aversion coefficients of the investors. The latter one only matters when the investors make a decision on how much to invest on the risky portfolio.
Thus the optimal risky portfolio can be constructed by maximizing its Sharpe ratio.
## Mathematical Description
```math
\max \frac{E(r_p)-r_f}{\sigma_p}

s.t.\ \  E(r_p)=w_0(\beta \mu + \alpha)+(1-w_0)\mu

\sigma_p = \sqrt{w_0^2(\beta^2\sigma^2+\sigma^2(\epsilon))+(1-w_0)^2\sigma^2+2w_0(1-w_0)\beta\sigma^2}
```
The above formula describe the problem strictly and naturally. By solving the optimal `$w_0$`, we can find the right way to construct the optimal risky portofio with Asset One and Asset Two.
## Alternative Description
We can construct a sythetic asset, called Asset Three by longing one share of Asset Two and shorting `$\beta$` share(s) of Asset One. Thus the return of Asset Three is `$\epsilon$` which is independent of `$r$`, the return of Asset One. Then the risky portfolio constructed with Asset One and Asset Two is identical to that of Asset One and Asset Three. This problem could be described as
```math
\max \frac{E(r_p)-r_f}{\sigma_p}

s.t.\ \  E(r_p)=w_0\alpha+(1-w_0)\mu

\sigma_p = \sqrt{w_0^2\sigma^2(\epsilon)+(1-w_0)^2\sigma^2}
```
which is much neater than before.

The first order condition (FOC) says
```math
\frac{\alpha -\mu}{\sigma_p}-\frac{E(r_p)-r_f}{\sigma_p^2}\cdot\frac{d\sigma_p}{dw_0}=0

\frac{d\sigma_p}{dw_0}=\frac{w_0\sigma^2(\epsilon)-(1-w_0)\sigma^2}{\sigma_p}
```
so
```math
w_0 = \frac{(\alpha-r_f) \sigma^2}{(\alpha-r_f) \sigma^2 + (\mu -r_f)\sigma^2(\epsilon)}

\frac{(E(r_p)-r_f)^2}{\sigma_p^2}=\frac{\alpha -\mu}{\sigma_p}\cdot\frac{\sigma_p}{w_0\sigma^2(\epsilon)-(1-w_0)\sigma^2}\cdot(E(r_p)-r_f)
```
together, we have
```math
S^2_p = \frac{(\alpha-r_f)^2}{\sigma^2(\epsilon)}+\frac{(\mu-r_f)^2}{\sigma^2}=S^2_{\alpha} + S^2_r

```
## The Final Results
For independent returns `$r$` and `$\epsilon$`, when constructing optimal portfolio based on them,
* weight of `$r$`: `$\frac{(\alpha-r_f)\sigma^2}{(\alpha-r_f)\sigma^2 + (\mu-r_f) \sigma^2(\epsilon)}$`
* weight of `$\epsilon$`: `$\frac{(\mu-r_f)\sigma^2(\epsilon)}{(\alpha-r_f)\sigma^2 + (\mu-r_f) \sigma^2(\epsilon)}$`
* their odd:
```math
\frac{(\alpha-r_f)\sigma^2}{(\mu-r_f)\sigma^2(\epsilon)}=\frac{\frac{\alpha-r_f}{\sigma^2(\epsilon)}}{\frac{(\mu-r_f)}{\sigma^2}}
```
In all, their optimal weights are proportional to `$\frac{\mu - r_f}{\sigma^2}$` :expected excess return devided by variance. This result is very interesting. Remember when we are facing only one risky asset, the optional allocation to the risky asset is

```math
\frac{1}{A} \cdot \frac{\mu - r_f}{\sigma^2}
```

Now for two INDEPENDENT risky assets, their optimal weights are still proportional to `$\frac{\mu -r_f}{\sigma^2}$`. Besides, the squared Sharpe Ratio of the optimal risky portfolio equals to the sum of squared Sharpe ratios of each assets.

# Homework And Open Book Midterm
1. Finish the proof of `$S^2_p = \frac{(\alpha-r_f)^2}{\sigma^2(\epsilon)}+\frac{(\mu-r_f)^2}{\sigma^2}=S^2_{\alpha} + S^2_r$`
2. Prove 8.22 in Investments by Bodie.
3. Prove 8.23 in Investments by Bodie.
4. Prove 8.21 in Investments by Bodie.
