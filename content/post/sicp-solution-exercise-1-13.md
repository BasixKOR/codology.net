---
title: "SICP - Solution: Exercise 1.13"
date: 2018-10-04T21:06:58+02:00
draft: false
type: posts
---

## Exercise 1.13

> Prove that ${\text{Fib}(n)}$ is the closest integer to ${\varphi^n/\sqrt5}$, where $\varphi={(1+\sqrt5)/2}$. Hint: Let $\psi={(1-\sqrt5)/2}$. Use induction and the definition of the Fibonacci numbers (see 1.2.2) to prove that ${\text{Fib}(n)}={(\varphi^n-\psi^n)/\sqrt5}$.

## Solution

The first step is to start from the definition of Fibonaci:

$$\text{Fib}(n) = \text{Fib}(n-1) + \text{Fib}(n-2)$$

And insert the definition we want to prove, ${\text{Fib}(n)}={(\varphi^n-\psi^n)/\sqrt5}$, on both side:

$$\frac{(\varphi^n-\psi^n)}{\sqrt5} =\frac{(\varphi^{n-1}-\psi^{n-1})}{\sqrt5} +\frac{(\varphi^{n-2}-\psi^{n-2})}{\sqrt5}$$

$$\varphi^n-\psi^n=\varphi^{n-1}-\psi^{n-1} +\varphi^{n-2}-\psi^{n-2}$$

$$\varphi^n-\psi^n=\frac{\varphi^n}\varphi-\frac{\psi^n}\psi+\frac{\varphi^n}{\varphi^2}-\frac{\psi^n}{\psi^2}$$

$$\varphi^n-\psi^n=\varphi^n\left(\frac1\varphi+\frac1{\varphi^2}\right)-\psi^n\left(\frac1\psi+\frac1{\psi^2}\right)$$

Now let's use the definition that $\varphi={(1+\sqrt5)/2}$ and $\psi={(1-\sqrt5)/2}$:

$$\varphi^n-\psi^n=\varphi^n\left(\frac1{(1+\sqrt5)/2}+\frac1{((1+\sqrt5)/2)^2}\right)-\psi^n\left(\frac1{(1-\sqrt5)/2}+\frac1{((1-\sqrt5)/2)^2}\right)$$

$$\varphi^n-\psi^n=\varphi^n\left(\frac2{(1+\sqrt5)}+\frac4{(1+\sqrt5)^2}\right)-\psi^n\left(\frac2{(1-\sqrt5)}+\frac4{(1-\sqrt5)^2}\right)$$

$$\varphi^n-\psi^n=\varphi^n\left(\frac{2(1+\sqrt5)}{(1+\sqrt5)^2}+\frac4{(1+\sqrt5)^2}\right)-\psi^n\left(\frac{2(1-\sqrt5)}{(1-\sqrt5)^2}+\frac4{(1-\sqrt5)^2}\right)$$

$$\varphi^n-\psi^n=\varphi^n\left(\frac{2(1+\sqrt5)+4}{(1+\sqrt5)^2}\right)-\psi^n\left(\frac{2(1-\sqrt5)+4}{(1-\sqrt5)^2}\right)$$

$$\varphi^n-\psi^n=\varphi^n\left(\frac{2+2\sqrt5+4}{1+2\sqrt5+5}\right)-\psi^n\left(\frac{2-2\sqrt5+4}{1-2\sqrt5+5}\right)$$

$$\varphi^n-\psi^n=\varphi^n\left(\frac{6+2\sqrt5}{6+2\sqrt5}\right)-\psi^n\left(\frac{6-2\sqrt5}{6-2\sqrt5}\right)$$

$$\varphi^n-\psi^n=\varphi^n-\psi^n$$

Thus proving that ${\text{Fib}(n)}={(\varphi^n-\psi^n)/\sqrt5}$ is true.

The next step is to notice that since $-1<\psi<0$ then $-1<\psi^n<1$.

And because $\sqrt5>2$ then we have:

$$-\frac{1}{2}<-\frac{1}{\sqrt5}<\frac{\psi^n}{\sqrt5}<\frac{1}{\sqrt5}<\frac{1}{2}$$

Now we can write ${\text{Fib}(n)}$ as two part:

$${\text{Fib}(n)}=\frac{(\varphi^n-\psi^n)}{\sqrt5}=\frac{\varphi^n}{\sqrt5}-\frac{\psi^n}{\sqrt5}$$

Which can be rewritten as:

$$\frac{\varphi^n}{\sqrt5}=\text{Fib}(n)+\frac{\psi^n}{\sqrt5}$$

We can add ${\text{Fib}(n)}$ to each side of:

$$-\frac{1}{2}<\frac{\psi^n}{\sqrt5}<\frac{1}{2}$$

So that:

$$\text{Fib}(n)-\frac{1}{2}<\text{Fib}(n)+\frac{\psi^n}{\sqrt5}<\text{Fib}(n)+\frac{1}{2}$$

Which means:

$$\text{Fib}(n)-\frac{1}{2}<\frac{\varphi^n}{\sqrt5}<\text{Fib}(n)+\frac{1}{2}$$

This shows that $\frac{\varphi^n}{\sqrt5}$ will never be further away from the value of $\text{Fib}(n)$ than $\pm\frac12$. Thus proving that that ${\text{Fib}(n)}$ is the closest integer to ${\varphi^n/\sqrt5}$.

### Update

A big thanks to Oliver Tušla for pointing out that since $\psi<0$ the initial proof needed fixing.
