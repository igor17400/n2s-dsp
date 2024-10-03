<style>
table tr:hover {
    background-color: #FFC0D9 !important;
}
</style>

# Signals

An <span style="background-color: #FF90BC;">analog signal</span> $ s $ is a finite real-valued function $ s(t) $ of a continuous variable $ t $ (called time), defined for all times on the interval $ -\infty < t < +\infty $. 

A <span style="background-color: #FF90BC;">digital signal</span> $ s $ is a **bounded** discrete-valued sequence $ S_n $ with a single index $ n $ (called discrete time), defined for all time $ n = -\infty, \cdots, +\infty $. <span style="background-color: #F9F9E0;">Bounded discrete values are exactly the kind of numbers represented by computer words with some finite number of bits.</span> 

Finiteness is a physical requirement and comes in three varieties: <span style="background-color: #F9F9E0;">finite signal value</span>, finite energy, and finite bandwidth.

## Definitions

### Continous Time Signals

````{prf:definition}
:label: energy

The <span style="background-color: #FF90BC;">energy</span> of a signal $ s $ is defined as:

$$
E_s = \int_{-\infty}^{\infty} |s(t)|^2 \, dt
$$
````

````{prf:definition}
:label: power

The <span style="background-color: #FF90BC;">power</span> of a signal $ s $ is defined as:

$$
P_s = \lim_{T \to \infty} \frac{1}{2T} \int_{-T}^{T} |s(t)|^2 \, dt
$$
````

````{prf:definition}
:label: rms

The Root Mean Square (RMS) of a signal $ s $ is defined as:

$$
RMS_s = \sqrt{\frac{1}{T} \int_{0}^{T} |s(t)|^2 \, dt}
$$
````

### Discrete Signals

For discrete signals, the definitions are adjusted to sums instead of integrals.

````{prf:definition}
:label: discrete-energy

The energy of a discrete signal $ S $ is defined as:

$$
E_S = \sum_{n=-\infty}^{\infty} |S_n|^2
$$
````

````{prf:definition}
:label: discrete-power

The power of a discrete signal $ S $ is defined as:

$$
P_S = \lim_{N \to \infty} \frac{1}{2N+1} \sum_{n=-N}^{N} |S_n|^2
$$
````

````{prf:definition}
:label: discrete-rms

The Root Mean Square (RMS) of a discrete signal $ S $ is defined as:

$$
RMS_S = \sqrt{\frac{1}{N} \sum_{n=0}^{N-1} |S_n|^2}
$$
````

### Bandwidth

The definition of bandwidth will be better discussed later. However, its understanding can be introduced now. It's a measure of speed, not size. A signal that fluctuates rapidly has a higher bandwidth than one that only varies slowly. <span style="background-color: #F9F9E0;">Requiring finite bandwidth imposes a smoothness constraint, disallowing sudden jump discontinuities and sharp corners.</span>

### Characteristics of Signals

Signals are characterized as being deterministic or stochastic. If deterministic, they can be periodic or non-periodic. If stochastic, they can be stationary or non-stationary. Additionally, signals can be finite or infinite in time duration, and they can have finite bandwidth or a full spectrum.

### The Vector Space of All Possible Signals

Can all possible signals be described in terms of some set of basic signals?

To use signals as bases for a vector space, they must obey the basic axioms of vector spaces. These include: 

1. **Addition**: Signal addition $ s = s_1 + s_2 $ according to $ s(t) = x(t) + y(t) $ and $ S_n = X_n + Y_n $.
2. **Zero Vector**: The constant signal $ S_n = 0 $ for all times $ n $.
3. **Inverse**: The inversion $ -s $ according to $ s(t) = -x(t) $ for all $ t $ and $ S_n = -X_n $ for all $ n $.
4. **Scalar Multiplication**: Multiplication by a real number $ a $ as $ s(t) = a x(t) $ for all $ t $ and $ S_n = a X_n $ for all $ n $.
5. **Inner Product**: The dot product as shown below:

$$
\langle s_1, s_2 \rangle = \int_{-\infty}^{\infty} s_1(t) s_2(t) \, dt
$$

For discrete signals:

$$
\langle S_1, S_2 \rangle = \sum_{n=-\infty}^{\infty} S_1(n) S_2(n)
$$

6. **Norm**: The energy as defined below:

````{prf:definition}
:label: norm-energy

The norm (or energy) of a signal $ s $ is:

$$
\|s\| = \sqrt{ \int_{-\infty}^{\infty} |s(t)|^2 \, dt }
$$
````

For discrete signals:

````{prf:definition}
:label: discrete-norm-energy

The norm (or energy) of a discrete signal $ S $ is:

$$
\|S\| = \sqrt{ \sum_{n=-\infty}^{\infty} |S_n|^2 }
$$
````

7. **Metric**: The energy of the difference signal obeys all the requirements:

````{prf:definition}
:label: metric-energy

The metric (or distance) between two signals $ s_1 $ and $ s_2 $ is:

$$
d(s_1, s_2) = \|s_1 - s_2\|
$$
````

For discrete signals:

````{prf:definition}
:label: discrete-metric-energy

The metric (or distance) between two discrete signals $ S_1 $ and $ S_2 $ is:

$$
d(S_1, S_2) = \|S_1 - S_2\|
$$
````
---

## *Examples*

### Analog Signal Example

Consider an analog signal $ s(t) = A \sin(2 \pi f t) $ where $ A $ is the amplitude and $ f $ is the frequency. The energy of this signal is given by:

$$
E_s = \int_{-\infty}^{\infty} |A \sin(2 \pi f t)|^2 \, dt = \infty \quad (\text{for periodic signals})
$$

The power of the signal is:

$$
P_s = \lim_{T \to \infty} \frac{1}{2T} \int_{-T}^{T} |A \sin(2 \pi f t)|^2 \, dt = \frac{A^2}{2}
$$

### Digital Signal Example

Consider a digital signal $ S_n = A \sin(2 \pi f n) $ where $ A $ is the amplitude and $ f $ is the frequency. The energy of this signal is:

$$
E_S = \sum_{n=-\infty}^{\infty} |A \sin(2 \pi f n)|^2 = \infty \quad (\text{for periodic signals})
$$

The power of the signal is:

$$
P_S = \lim_{N \to \infty} \frac{1}{2N+1} \sum_{n=-N}^{N} |A \sin(2 \pi f n)|^2 = \frac{A^2}{2}
$$


## Vector Space of Signals

Since signals form a vector space, the theorems of linear algebra guarantee that there is a <span style="background-color: #F9F9E0;">basis</span> $ \{ \phi_k \} $, i.e., a set of signals in terms of which any signal $ s $ can be expanded:

$$
s = \sum_k c_k \phi_k
$$

From linear algebra, we know that <span style="background-color: #F9F9E0;">every vector has a basis</span>, but in general, this basis is not unique. Similarly, for the vector space of signals, there is a lot of flexibility in the choice of basis. The most common choices are based on signals we have already met, namely <span style="background-color: #F9F9E0;">shifted unit impulses (SUIs)</span> and sinusoids.

### Shifted Unit Impulses (SUI)

Shifted Unit Impulses $ S_n $ are defined as:

$$
S_n = \delta_{nm}
$$

where $ \delta_{nm} $ equals one when $ n = m $, and zero for all other times.

### Sinusoids

Sinusoids are another common basis for signals. When we represent a signal by expanding it in the basis of SUIs, we say that the signal is in the time domain. When we use the basis of sinusoids, we say that the signal is in the frequency domain.

### Expansion of Digital Signals

We can expand any digital signal in terms of SUIs as follows:

$$
S_n = \sum_{m=-\infty}^{\infty} S_m \delta_{nm}
$$

This proves that these signals span the entire space. No two SUIs overlap; they are orthogonal and linearly independent (no $ S_{nm} $ can be expanded in terms of others), and so they form a valid basis.

## Most Common Signals

| Signal Name           | Continuous Format                   | Digital Format                     |
|-----------------------|--------------------------------------|------------------------------------|
| Unit Constant         | $ s(t) = A $                      | $ S_n = A $                      |
| Unit Step             | $ s(t) = u(t) $                   | $ S_n = u[n] $                   |
| Unit Impulse          | $ s(t) = \delta(t) $              | $ S_n = \delta[n] $              |
| Square Wave           | $ s(t) = A \cdot \text{sgn}(\sin(\omega t)) $ | $ S_n = A \cdot \text{sgn}(\sin(\omega n)) $ |
| Sinusoid              | $ s(t) = A \cdot \sin(\omega t + \phi) $ | $ S_n = A \cdot \sin(\omega n + \phi) $|
| Damped Sinusoid       | $ s(t) = A e^{-\alpha t} \sin(\omega t) $ | $ S_n = A e^{-\alpha n} \sin(\omega n) $ |
| Real Exponential      | $ s(t) = A e^{\alpha t} $         | $ S_n = A e^{\alpha n} $         |
| Complex Sinusoid      | $ s(t) = A e^{j(\omega t + \phi)} $ | $ S_n = A e^{j(\omega n + \phi)} $ |
| Damped Complex Sinusoid| $ s(t) = A e^{-\alpha t} e^{j(\omega t + \phi)} $ | $ S_n = A e^{-\alpha n} e^{j(\omega n + \phi)} $ |
