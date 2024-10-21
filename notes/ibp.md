# Scattering Amplitudes Lecture on 07 Nov: Integration-by-Parts Reduction

## Toy example: IBP for tadpole integrals
To be completed... Compare with analytic formula.

## Basic setup for bubble example
Let's look at the bubble family of integrals,
@@img-tiny ![one-loop bubble](/notes/bubble.svg) @@
\begin{aligned}
I_{\nu_1, \nu_2} &= \int d^d q \frac{1} {(q^2-m^2)^{\nu_1} [(p+q)^2-m^2]^{\nu_2}} \\
&= \int d^d q \frac 1 {\rho_1^{\nu_1} \, \rho_2^{\nu_2}} \, ,
\end{aligned}
where we defined
\begin{equation}
\rho_1 = q^2 - m^2, \quad \rho_2 = (p+q)^2-m^2 \, .
\end{equation}
We can invert the above equation to write any dot product involving the loop momentum $q$ in terms of inverse propagator variables,
\begin{equation}
q^2 = \rho_1 + m^2, \quad p \cdot q = \frac 1 2 (\rho_2 - \rho_1 - p^2) \, .
\end{equation}
We can write down the IBP identity
\begin{align}
0 &= \int d^d q \frac{\partial}{\partial q^\mu} {\frac{q^\mu}{\rho_1^{\nu_1} \rho_2^{\nu_2}}} \\
&= \int d^d q \left[ \frac d {\rho_1^{\nu_1} \rho_2^{\nu_2}}
 - \frac {\nu_1} {\rho_1^{\nu_1+1} \rho_2^{\nu_2}} \, q^\mu \frac{\partial}{\partial q^\mu} \rho_1
 - \frac {\nu_2} {\rho_1^{\nu_1} \rho_2^{\nu_2+1}} \, q^\mu \frac{\partial}{\partial q^\mu} \rho_2
\right]
\end{align}
Using Eqs. (2) and (3), we have
\begin{align}
q^\mu \frac{\partial}{\partial q^\mu} \rho_1 &= 2 q^2 = 2 \rho_1 + 2m^2 \\
q^\mu \frac{\partial}{\partial q^\mu} \rho_2 &= 2 p \cdot q + 2 q^2 = \rho_1 + \rho_2 + 2m^2 - p^2 \, .
\end{align}
The IBP identity in the 2nd line of Eq. (4) evaluates to
\begin{align}
0 = (d-2\nu_1-\nu_2) I_{\nu_1, \nu_2} - 2\nu_1 m^2 I_{\nu_1+1, \nu_2} - \nu_2 I_{\nu_1-1, \nu_2+1} - \nu_2 (2m^2-p^2) I_{\nu_1, \nu_2+1}
\end{align}

## Simple application to differential equations
Substituting $\nu_1=1, \nu_2=0$ in Eq. (6) gives
\begin{equation}
0 = (d-2) I_{1,0} - 2m^2 I_{2,0} \implies I_{2,0} = \frac{1}{2m^2} (d-2) I_{1,0}
\end{equation}

Substituting $\nu_1=\nu_2=1$ and using symmetry relations $I_{1,2}=I_{2,1}, \, I_{0,2}=I_{2,0}$ gives
\begin{equation}
0 = (d-3) I_{1,1} - (4m^2-p^2) I_{1,2} - I_{0,2} \, .
\end{equation}
Combined with Eq. (7), we obtain
\begin{equation}
I_{1,2} = \frac{d-3}{4m^2-p^2} I_{1,1} - \frac{d-2}{2m^2(4m^2-p^2)} I_{1,0} \, .
\end{equation}

By directly differentiating w.r.t. $m^2$ under the integral sign in Eq. (1), we obtain differential equations for the unknown integrals $(I_{1,0}, I_{1,1})$,
\begin{align}
\frac {\partial}{\partial m^2} \begin{pmatrix} I_{1,1} \\ I_{1,0} \end{pmatrix}
= \begin{pmatrix} 2 I_{1,2} \\ I_{2,0} \end{pmatrix}
= \begin{pmatrix} \frac{2(d-3)}{4m^2-p^2} & - \frac{d-2}{m^2(4m^2-p^2)} \\ 0 & \frac{d-2}{2m^2} \end{pmatrix} \cdot \begin{pmatrix} I_{1,1} \\ I_{1,0} \end{pmatrix}
\end{align}

## Systematic reduction of all possible bubble integrals
To be completed...

## Using FIRE software to automate IBP reduction

You need to have Wolfram Mathematica installed.

On Linux or Mac, install FIRE 6.5 with the following command in the terminal:
```
git clone https://gitlab.com/feynmanIntegrals/fire.git
```
We'll skip the installation of the C++ version of FIRE, since we'll only use the Mathematica version here.

Navigate into the `examples/` folder:
```
cd fire/FIRE6/examples
```
and open the example notebook `box.nb`. You only need to look at the first half of the notebook, leading to the reduction result for `F[1, {2, 2, 2, 2}]`, i.e. the box integral with all four propagators raised to a 2nd power.
