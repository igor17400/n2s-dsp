# Common Fourier Transform Properties

The Fourier Transform has several fundamental properties that make it a powerful tool for signal analysis. These properties allow us to analyze and manipulate signals in the frequency domain and provide a deeper understanding of how different transformations affect a signal's spectral content.

## 1. Linearity Property

The **linearity property** states that if $x(t)$ and $y(t)$ are two signals with corresponding Fourier Transforms $X(f)$ and $Y(f)$, then the Fourier Transform of a linear combination of these signals is given by:

$$
\boxed{ \mathcal{F} \{ a x(t) + b y(t) \} = a X(f) + b Y(f) }
$$

where $a$ and $b$ are constants. This property is useful for analyzing systems that are linear, such as electrical circuits and control systems.

## 2. Time Shifting Property

If a signal $x(t)$ is shifted in time by $t_0$, its Fourier Transform is given by:

$$
\boxed{ \mathcal{F} \{ x(t - t_0) \} = X(f) e^{-j2\pi ft_0} }
$$

This property indicates that a time shift in the time domain results in a **phase shift** in the frequency domain.

## 3. Frequency Shifting Property

If a signal $x(t)$ is multiplied by a complex exponential $e^{j2\pi f_0 t}$, its Fourier Transform is shifted in the frequency domain:

$$
\boxed{ \mathcal{F} \{ x(t) e^{j2\pi f_0 t} \} = X(f - f_0) }
$$

This property is commonly used in modulation and demodulation of signals in communication systems.

## 4. Time Scaling Property

If a signal $x(t)$ is scaled in time by a factor of $a$, its Fourier Transform is given by:

$$
\boxed{ \mathcal{F} \{ x(at) \} = \frac{1}{|a|} X\left( \frac{f}{a} \right) }
$$

Time scaling results in an **inverse scaling** in the frequency domain. This means that compressing a signal in the time domain (making it shorter) results in expanding it in the frequency domain.

## 5. Conjugate Symmetry Property

If $x(t)$ is a **real-valued** signal, then its Fourier Transform $X(f)$ satisfies the **conjugate symmetry** property:

$$
\boxed{ X(-f) = X^*(f) }
$$

This means that the Fourier Transform of a real signal has **symmetrical magnitudes** and **opposite phases** at positive and negative frequencies.

## 6. Parseval's Theorem

The **Parseval's theorem** relates the total energy of a signal in the time domain to its energy in the frequency domain:

$$
\boxed{ \int_{-\infty}^{\infty} |x(t)|^2 \, dt = \int_{-\infty}^{\infty} |X(f)|^2 \, df }
$$

This property is important in signal processing for understanding energy conservation and power spectral density.

## 7. Duality Property

If $x(t)$ has a Fourier Transform $X(f)$, then the duality property states that:

$$
\boxed{ \mathcal{F} \{ X(t) \} = x(-f) }
$$

This property swaps the roles of the time and frequency domains, allowing us to use the time-domain properties in the frequency domain.

## Summary Table of Fourier Transform Properties

<style>
table tr:hover {
    background-color: #FFC0D9 !important;
}
</style>

| **Property**                | **Time Domain**                                  | **Frequency Domain**                                        |
|-----------------------------|--------------------------------------------------|------------------------------------------------------------|
| **Linearity**               | $a x(t) + b y(t)$                                | $a X(f) + b Y(f)$                                           |
| **Time Shifting**           | $x(t - t_0)$                                      | $X(f) e^{-j2\pi f t_0}$                                     |
| **Time Scaling**            | $x(at)$                                           | $\frac{1}{|a|} X\left( \frac{f}{a} \right)$                  |
| **Time Reversal**           | $x(-t)$                                           | $X(-f)$                                                     |
| **Duality**                 | $X(t)$                                            | $x(-f)$                                                     |
| **Frequency Shifting**      | $x(t) e^{j2\pi f_0 t}$                            | $X(f - f_0)$                                                |
| **Convolution**             | $x(t) * y(t)$                                     | $X(f) \cdot Y(f)$                                           |
| **Differentiation**         | $\frac{d^n}{dt^n} x(t)$                           | $(j 2\pi f)^n X(f)$                                         |
| **Integration**             | $\int_{-\infty}^{t} x(\tau) \, d\tau$             | $\frac{1}{j2\pi f} X(f) + \frac{1}{2} \delta(f)$             |
