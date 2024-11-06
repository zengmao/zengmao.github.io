# Scattering Amplitudes Lecture on 07 Nov: (2) Integration-by-Parts Reduction

## Toy example: IBP for tadpole integrals
Let's look at the simplest toy example, the family of one-loop tadpole integrals with internal mass $m$,
@@img-moretiny ![one-loop tadpole](/notes/tadpole.svg) @@
\begin{aligned}
I_{\nu} &= \int \frac {d^D k}{i \pi^{D/2}} \frac{1} {(-k^2+m^2)^{\nu}} \\
&= \int \frac {d^D k}{i \pi^{D/2}} \frac 1 {\rho^{\nu}} \, ,
\end{aligned}
where we defined
\begin{equation}
\rho = -k^2 + m^2 \, .
\end{equation}
The IBP identity is
\begin{align}
0 &= \int \frac {d^D k}{i \pi^{D/2}} \frac{\partial}{\partial k^\mu} \frac{k^\mu}{\rho^{\nu} }
&= \int \frac {d^D k}{i \pi^{D/2}} \left[  \frac {D} {\rho^\nu} - \frac {\nu} {\rho^{\nu+1}} k^\mu \frac{\partial}{\partial k^\mu} \rho \right] \, .
\end{align}
We use
\begin{equation}
k^\mu \frac{\partial}{\partial k^\mu} \rho = -2k^2 = 2 (\rho - m^2) \, .
\end{equation}
The IBP identity becomes
\begin{equation}
0  = \int \frac {d^D k}{i \pi^{D/2}} \left[ \frac {D - 2 \nu} {\rho^\nu} + \frac{2 m^2 \nu}{\rho^{\nu+1}} \right] = (D-2\nu) I_\nu + 2m^2 \nu I_{\nu+1} \, .
\end{equation}
The exact result with $D=4-2\epsilon$ is
\begin{equation}
I_\nu = \frac {\Gamma(\nu-D/2)} {\Gamma(\nu)} \frac 1 {(m^2)^{\nu-D/2}} \, .
\end{equation}
The IBP identity agrees with the exact result using the gamma function relations $\Gamma(\nu+1) = \nu \Gamma(\nu)$, $\Gamma(\nu+1-D/2) = (\nu-D/2) \Gamma(\nu-D/2)$.

## Basic setup for bubble example
Let's look at the bubble family of integrals,
@@img-tiny ![one-loop bubble](/notes/bubble.svg) @@
\begin{aligned}
I_{\nu_1, \nu_2} &= \int \frac {d^D k}{i \pi^{D/2}} \frac{1} {(-k^2+m^2)^{\nu_1} [-(p-k)^2+m^2]^{\nu_2}} \\
&= \int \frac {d^D k}{i \pi^{D/2}} \frac 1 {\rho_1^{\nu_1} \, \rho_2^{\nu_2}} \, ,
\end{aligned}
where we defined
\begin{equation}
\rho_1 = -k^2 + m^2, \quad \rho_2 = -(p-k)^2+m^2 \, .
\end{equation}
We can invert the above equation to write any dot product involving the loop momentum $k$ in terms of inverse propagator variables,
\begin{equation}
k^2 = -\rho_1 + m^2, \quad p \cdot k = \frac 1 2 (\rho_2 - \rho_1 + p^2) \, .
\end{equation}
We can write down the IBP identity
\begin{align}
0 &= \int \frac {d^D k}{i \pi^{D/2}} \frac{\partial}{\partial k^\mu} {\frac{k^\mu}{\rho_1^{\nu_1} \rho_2^{\nu_2}}} \\
&= \int \frac {d^D k}{i \pi^{D/2}} \left[ \frac D {\rho_1^{\nu_1} \rho_2^{\nu_2}}
 - \frac {\nu_1} {\rho_1^{\nu_1+1} \rho_2^{\nu_2}} \, k^\mu \frac{\partial}{\partial k^\mu} \rho_1
 - \frac {\nu_2} {\rho_1^{\nu_1} \rho_2^{\nu_2+1}} \, k^\mu \frac{\partial}{\partial k^\mu} \rho_2
\right]
\end{align}
Using Eqs. (8) and (9), we have
\begin{align}
k^\mu \frac{\partial}{\partial k^\mu} \rho_1 &= -2 k^2 = 2 \rho_1 - 2m^2 \\
k^\mu \frac{\partial}{\partial k^\mu} \rho_2 &= 2 p \cdot k - 2 k^2 = \rho_1 + \rho_2 - 2m^2 + p^2 \, .
\end{align}
The IBP identity in the 2nd line of Eq. (4) evaluates to
\begin{align}
0 = (D-2\nu_1-\nu_2) I_{\nu_1, \nu_2} + 2\nu_1 m^2 I_{\nu_1+1, \nu_2} - \nu_2 I_{\nu_1-1, \nu_2+1} + \nu_2 (2m^2-p^2) I_{\nu_1, \nu_2+1}
\end{align}

## Simple applications
Substituting $\nu_1=1, \nu_2=0$ in Eq. (12) gives
\begin{equation}
0 = (D-2) I_{1,0} + 2m^2 I_{2,0} \implies I_{2,0} = -\frac{1}{2m^2} (D-2) I_{1,0}
\end{equation}

Substituting $\nu_1=\nu_2=1$ and using symmetry relations $I_{1,2}=I_{2,1}, \, I_{0,2}=I_{2,0}$ gives
\begin{equation}
0 = (D-3) I_{1,1} + (4m^2-p^2) I_{1,2} - I_{0,2} \, .
\end{equation}
Combined with Eq. (13), we obtain
\begin{equation}
I_{1,2} = -\frac{D-3}{4m^2-p^2} I_{1,1} - \frac{D-2}{2m^2(4m^2-p^2)} I_{1,0} \, .
\end{equation}

<!-- By directly differentiating w.r.t. $m^2$ under the integral sign in Eq. (7), we obtain differential equations for the unknown integrals $(I_{1,0}, I_{1,1})$, -->
<!-- \begin{align} -->
<!-- \frac {\partial}{\partial m^2} \begin{pmatrix} I_{1,1} \\ I_{1,0} \end{pmatrix} -->
<!-- = \begin{pmatrix} -2 I_{1,2} \\ -I_{2,0} \end{pmatrix} -->
<!-- = \begin{pmatrix} \frac{2(D-3)}{4m^2-p^2} & + \frac{D-2}{m^2(4m^2-p^2)} \\ 0 & \frac{D-2}{2m^2} \end{pmatrix} \cdot \begin{pmatrix} I_{1,1} \\ I_{1,0} \end{pmatrix} -->
<!-- \end{align} -->
<!-- The differential equations can be solved with appropriate boundary conditions, as will be covered by future lectures. -->
**Exercise 1a:** Combine with dimension shifting identities to express $I_{1,1}(D)$ in terms of $I_{1,1}(D+2)$ and $I_{1,0}(D+2)$.

**Exercise 1b:** Invert the above results to obtain $I_{1,1}(D)$ in terms of $I_{1,1}(D-2)$ and $I_{1,0}(D-2)$.

## Systematic reduction of all possible bubble integrals
Here we present a systematic method for solving IBP relations bubble integral. The method will be applicable to many other Feynman integrals. We will reduce bubble integrals $I_{\nu_1, \nu_2}$ with any integer indices $\nu_1, \nu_2$ without relying on symmetry relations. All we need is one more IBP identity besides Eq. (10), by changing $k^\mu$ in the numerator to $p^\mu$. (For a general integral family, we allow the numerator to be any of the independent external and loop momenta.)
The calculation steps are exactly analogous to those leading to Eq. (12), and we just quote the final result which is the counterpart of Eq. (12),
\begin{equation}
0 = (\nu_2-\nu_1) I_{\nu_1, \nu_2} + \nu_1 I_{\nu_1+1, \nu_2-1} - \nu_2 I_{\nu_1-1, \nu_2+1} + \nu_1 p^2 I_{\nu_1+1, \nu_2} - \nu_2 p^2 I_{\nu_1, \nu_2+1} \, .
\end{equation}

Eq. (12) and Eq. (17) involve a total of 5 integrals, for every choice of integers $(\nu_1, \nu_2)$. The integrals involved in the two linear relations are visualized on the $(\nu_1, \nu_2)$ lattice,
@@img ![bubble_ibp_grid](/notes/bubble_ibp_grid.svg) @@
For the sake of solving the system, we define an auxiliary quantity, the *complexity* of an integral $I_{\nu_1, \nu_2}$, to be $\nu_1+\nu_2$. We want to solve more "complex" integrals in terms of less complex ones. Two of the integrals have the same complexity. Fortunately, we have two IBP identities Eq. (12) and (17) which allow us to solve both integrals in terms of the three less complex integrals - the $2\times 2$ linear system is non-degenerate if $\nu_1 \geq 1, \nu_2 \geq 1$. The results are called *reduction rules*,
\begin{align}
I_{\nu_1 + 1, \nu_2} = \frac{1}{p^2 (4m^2-p^2)}
& \bigg[
-(2m^2-p^2) I_{\nu_1+1, \nu_2-1} + 2\frac{\nu_2}{\nu_1} m^2 I_{\nu_1-1, \nu_2+1} \\
& \quad - \frac {Dp^2 - \nu_1(2m^2+p^2) + 2\nu_2(m^2-p^2)}{\nu_1} I_{\nu_1, \nu_2}
\bigg] \, , \\
I_{\nu_1, \nu_2+1} = \frac{1}{p^2 (4m^2-p^2)}
& \bigg[
-(2m^2-p^2) I_{\nu_1-1, \nu_2+1} + 2\frac{\nu_1}{\nu_2} m^2 I_{\nu_1+1, \nu_2-1} \\
& \quad - \frac {Dp^2 - \nu_2(2m^2+p^2) + 2\nu_1(m^2-p^2)}{\nu_2} I_{\nu_1, \nu_2}
\bigg] \, .
\end{align}
Furthermore, the tadpole IBP identity Eq. (5) can be reused,
\begin{equation}
(D-2\nu_1) I_{\nu_1,0} + 2m^2 \nu_1 I_{\nu_1+1,0} = 0 , \quad (D-2\nu_2) I_{0, \nu_2} + 2m^2 \nu_2 I_{0, \nu_2+1} = 0 \, .
\end{equation}
Applying these reduction rules iteratively, we reduce the complexity of the integrals until all integral are reduced to the *master integrals*, $I_{1,1}$, $I_{2,0}$ and $I_{0,2}$, marked as green squares in the plot.

**Exercise 2:** Reduce $I_{2,2}$ to a linear combination of master integrals $I_{1,1}$ and $I_{1,0}$. Then write a program to reduce any $I_{\nu_1, \nu_2}$ for $\nu_1, \nu_2 \geq 1$.

<!-- ## Using FIRE software to automate IBP reduction (skipped in lecture) -->

<!-- You need to have Wolfram Mathematica installed. -->

<!-- On Linux or Mac, install FIRE 6.5 with the following command in the terminal: -->
<!-- ``` -->
<!-- git clone https://gitlab.com/feynmanIntegrals/fire.git -->
<!-- ``` -->
<!-- We'll skip the installation of the C++ version of FIRE, since we'll only use the Mathematica version here. -->

<!-- Navigate into the `examples/` folder: -->
<!-- ``` -->
<!-- cd fire/FIRE6/examples -->
<!-- ``` -->
<!-- and open the example notebook `box.nb`. You only need to look at the first half of the notebook, leading to the reduction result for `F[1, {2, 2, 2, 2}]`, i.e. the box integral with all four propagators raised to a 2nd power. -->

## Advanced topics:

- For more complicated integrals, deriving reduction rules is very nontrivial and often prohibitive. Instead, a systematic method known as the *Laporta algorithm* is used to automate IBP reduction. Some public codes include e.g. LiteRed, FIRE, Kira. Future lectures will rely on results obtained from such software without further derivation.

- The number of master integrals is finite for any integral family. There is some geometric understanding, e.g. in terms of the Euler characteristics of the singular surface of the $U+F$ polynomial in the Lee-Pomeransky representation, or in terms of critical points of maximal-cut integrals in the Baikov representation. The mathematical language of *twisted cohomology* formalizes the concepts of IBP reduction and the number of master integrals.
