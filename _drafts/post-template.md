---
# HOW TO USE THIS TEMPLATE
# 1. Copy this file into _posts/ and rename it to YYYY-MM-DD-short-title.md
#    (e.g. _posts/2026-11-01-regret-bounds.md). The date in the name is the post date.
# 2. Edit the fields below, write your post, then git push.
# Files in _drafts/ are NOT published, so this template never appears on the site.
layout: post
title: Writing Math in a Blog Post
description: A short template showing how to write LaTeX in posts
tags: online-learning
giscus_comments: true # comments at the bottom of the post
featured: false # true pins the post at the top of the blog page
toc:
  sidebar: left # table of contents on the left; delete these two lines to hide it
---

Write normal text in Markdown: **bold**, _italic_, [links](https://masoumian.github.io), and lists.

## Inline math

Put inline math between single or double dollar signs: the regret after $T$ rounds is $R_T = \sum_{t=1}^T \ell_t(a_t) - \min_{a} \sum_{t=1}^T \ell_t(a)$.
If an inline formula looks wrong, use double dollars instead: $$\mathbb{E}[R_T] = O(\sqrt{T \log K})$$.
To write a literal dollar sign, type `\$`.

## Display equations

Put display equations between `$$` lines, with a blank line before and after:

$$
\rho^* = \max_{\pi} \lim_{T \to \infty} \frac{1}{T} \, \mathbb{E}^{\pi}\left[\sum_{t=1}^{T} r(s_t, a_t)\right]
$$

## Numbered equations and references

Use `\begin{equation}` with a `\label`, then refer to it with `\eqref`:

$$
\begin{equation}
\label{eq:bellman}
\rho^* + h^*(s) = \max_{a} \Big[ r(s,a) + \sum_{s'} P(s' \mid s, a) \, h^*(s') \Big]
\end{equation}
$$

Equation \eqref{eq:bellman} is the average-reward Bellman equation.

## Aligned equations

$$
\begin{align}
R_T &= \sum_{t=1}^T \big(\rho^* - r_t\big) \\
    &\le \tilde{O}\big(\mathrm{sp}(h^*) \sqrt{SAT}\big)
\end{align}
$$

## Theorem-style blocks

<!-- prettier-ignore-start -->
> ##### Theorem 1
>
> For any $\delta \in (0,1)$, with probability at least $1-\delta$, the regret satisfies $R_T \le C \sqrt{T \log(1/\delta)}$.
{: .block-tip }
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
> ##### Remark
>
> Use `.block-tip` (green), `.block-warning` (yellow), or `.block-danger` (red).
{: .block-warning }
<!-- prettier-ignore-end -->

## Images and PDFs

Put images in `assets/img/` and show them like this:

{% raw %}

```liquid
{% include figure.liquid loading="eager" path="assets/img/my-figure.png" class="img-fluid rounded" zoomable=true %}
```

{% endraw %}

Link a PDF the usual way: [read the PDF](/assets/pdf/blog/On_Regrets.pdf).

## Footnotes

A sentence with a footnote.[^1]

[^1]: The footnote text appears at the bottom of the post.
