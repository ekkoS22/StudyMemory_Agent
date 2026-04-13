# ECE301 - DTFT

## Q15 DTFT of Right-Sided Exponential

### Problem

Compute the discrete-time Fourier transform $F(\omega)$ of the signal

$$
f[n]=\left(\frac{3}{4}\right)^n u[n]
$$

### Solution

By definition, the DTFT is

$$
F(\omega)=\sum_{n=-\infty}^{\infty} f[n]e^{-j\omega n}
$$

Since $u[n]$ makes the signal start at $n=0$,

$$
F(\omega)=\sum_{n=0}^{\infty}\left(\frac{3}{4}\right)^n e^{-j\omega n}
$$

Combine the terms inside the power:

$$
F(\omega)=\sum_{n=0}^{\infty}\left(\frac{3}{4}e^{-j\omega}\right)^n
$$

This is a geometric series:

$$
\sum_{n=0}^{\infty}r^n=\frac{1}{1-r}
$$

Here,

$$
r=\frac{3}{4}e^{-j\omega}
$$

Therefore,

$$
F(\omega)=\frac{1}{1-\frac{3}{4}e^{-j\omega}}
$$

### Key Idea

A right-sided exponential $a^n u[n]$ has DTFT

$$
\frac{1}{1-ae^{-j\omega}}
$$

when $|a|<1$.

### Common Mistake

- Starting the sum at $n=-\infty$ instead of $n=0$.
- Forgetting the $e^{-j\omega n}$ term in the DTFT definition.
- Writing the answer as $\frac{1}{1-\frac{3}{4}}$ and ignoring the frequency term.
