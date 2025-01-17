+++
title = 'How to measure the non-Markovianity of a Quantum System?'
date = 2023-07-26T08:11:59-05:00
draft = false
categories = ["math"]
+++

<div style="text-align: center;">
    Final term paper for the course of Open Quantum Systems.
</div>

# Introduction 

Master equations govern the time evolution of a quantum system interacting with an environment and can be written in a variety of forms. Time-independent or memoryless master equations can be expressed in the well-known Lindblad form. In fact, any master equation local in time, Markovian or non-Markovian, can also be written in a Lindblad-like form. A diagonalization procedure results in a unique, canonical representation of the equation, which can be used to fully characterize the non-Markovianity of the time evolution. Several different measures of non-Markovianity have recently been presented that reflect, to different degrees, the appearance of negative decoherence rates in the Lindblad-like form of the master equation. We therefore propose to use the negative decoherence rates themselves as they appear in the canonical form of the master equation to fully characterize non-Markovianity.

# Characterizing the non-Markovianity
To be more precise we say that the canonical form is to bring the master equation to a local form such that the coherence rate is uniquely defined. Let us look at the method used in the paper. Recall the master equation in local time

{{< rawhtml >}}
$$
\begin{align*}
    \dot{\rho}(t) &= \int_0^t ds (K_{s,t} \circ \phi_s)[\rho(0)] \\
    &= \int_0^t ds (K_{s,t} \circ \phi_s \circ \phi^{-1}_t) \phi_t[\rho(0)] \\
    &= \Lambda_t[\rho(t)]
\end{align*}
$$
{{< /rawhtml >}}


We can write this as 
$$
    \dot{\rho}=\Lambda_t[\rho]=\sum_kA_k(t)\rho B^\dagger_k(t)
$$
We say that we have $N$ operators $ \\{G_m | m=0,1,2,...,N-1\\} $ such that they have the following properties: $\big\\{G_0=\frac{\hat{1}}{\sqrt{d}},\quad G_m=G_m^\dagger,\quad Tr[G_mG_n]=\delta_{mn}\big\\}$
With this new operator base we can expand $A_k$ and $B_k$ such that $
A_k=\sum_i G_ia_{ik};\quad B_k=\sum_j G_jb_{jk}$
We replace that in the master equation
$$
    \dot\rho=\sum_k\sum{ij}a_{ik}b_{jk}^*G_i\rho G_j=\sum_{ij}c_{ij}G_i\rho G_j
$$
We use the property $G_m=G^\dagger_m$, and that $\rho$ and $\dot\rho$ are Hermitian $
\sum_{ij}c_{ij}G_i\rho G_j=\sum_{ij}c_{ij}^*G_j\rho G_i=\sum_{ij}c_{ij}^*G_i\rho G_j$. We separate the terms with index $0$

$$
\dot\rho=\sum_{ij}c_{ij}^*G_i\rho G_j=c_{00}G_0\rho G_0+\sum_ic_{0i}^*G_i\rho G_0+\sum_j c_{j0}^*G_0\rho G_j+\sum_{i\neq j}C_{ji}^*G_i\rho G_j
$$

We use the base definition of $G_0=\frac{\hat{1}}{\sqrt{d}}$:

{{< rawhtml >}}
\[
    \dot\rho=\sum_{ij}c_{ij}^*G_i\rho G_j=c_{00}\frac{\rho}{d}+\sum_i c_{0i}^*G_i\frac{\rho}{\sqrt{d}}+\sum_j c_{j0}^{*}\frac{\rho}{\sqrt{d}} G_j+\sum_{i\neq j}C_{ji}^*G_i\rho G_j
\]
{{< /rawhtml >}}


Identifying  $C=\frac{1}{2}\frac{c_{00}}{d}+\sum_i \frac{c_{i0}}{\sqrt{d}}G_i$ we get:

$$
    \dot\rho=C\rho+\rho C^\dagger+\sum_{i\neq j}C_{ji}^*G_i\rho G_j
$$

If we apply the trace and its cyclic property to rearrange the position of $rho$ and taking into account that $Tr[\dot\rho]$ such that we obtain: $C+C^\dagger=-\sum_{i,j=1}^{N-1}d_{ij}G_jG_i$. We identify $H=\frac{1}{2}i\hbar (C-C^\dagger)$ then we can write
$$
    \dot\rho=-\frac{i}{\hbar}[H,\rho]+\sum_{i,j=1}^{N-1}d_{ij}(t)\Big(G_i\rho G_j-\frac{1}{2}{G_jG_i,\rho}\Big)
$$
The inconsistency matrix $\textbf{d}$ is independent of time. Due to the above construction we say that the matrix elements have the following expression
$$
d_{ij}=\sum_kTr[G_iA_k]Tr[G_jB_k\dagger]
$$
This can also be written in its diagonal form since it is Hermitian.
$$
d_{ij}=\sum_kU_{ik}\gamma_kU_{jk}^*
$$
where the eigenvalues ​​$\gamma_k$ of $\textbf{d}$ are real, but not necessarily positive at all times, and the $U_{ik}$ are unitary matrices made of the same eigenvectors of $\textbf{d}$, with $\sum_kU_{ik}U_{jk}^*=\delta_{ij}$. Now to recover the expression of the master equation we use the properties of the basis ${G_m}$ and define $L_k(t)=\sum_{i=1}^{N-1}U_{ik}(t)G_i$, then, recovering the time dependence, we get

$$
    \dot\rho=-\frac{i}{\hbar}[H(t),\rho]+\sum_{k=1}^{d^2-1}\gamma_k(t)\Big\[L_k(t)\rho L_k^\dagger(t)-\frac{1}{2}\big\\{L_k^\dagger(t)L_k(t),\rho \big\\}\Big\]
$$

It can be noted that the equation is similar to the Lindblad equation for a memoryless master equation. However, we list some differences:
- La dependencia de tiempo de la tasa de decoherencia y los operadores $L_k$
- Las tasas de decoherencia están únicamente determinadas
- Las tasa de decoherencia puede ser negativa, correspondiendo a interacciones entre el ambiente y el sistema de tal manera que el sistema podría "recobrar coherencia", es decir, revertir el proceso de decaimientos más tempranos

If the canonical decoherence rates are positive at all times, then the evolution over any time interval is completely positive. Moreover, for finite systems, having positive decoherence rates at all times is equivalent to divisibility of the evolution to a sequence of infinitesimally positive evolutions.


**Non-Markovian processes:** We now state the following definition of non-Markovianity: a local master equation is _Markovian_ at a given time if and only if the canonical decoherence rates are positive. Likewise, the evolution is _non-Markovian_ if one or more of the decoherence rates are strictly negative. We give two examples where it can be more easily seen what we mean. Let us say that we have the following law of evolution

{{< rawhtml >}}
\[
\begin{align*}
        \dot\rho&=[2\gamma(t)+\tilde\gamma(t)][2\sigma_x\rho\sigma_x+2\sigma_y\rho\sigma_y-4\rho]\\
        &-\gamma(t)[2\sigma_-\rho\sigma_+-\sigma_+\sigma_-\rho-\rho\sigma_+\sigma_-]\\
        &-\gamma(t)[2\sigma_+\rho\sigma_--\sigma_-\sigma_+\rho-\rho\sigma_-\sigma_+]
\end{align*}
\]
{{< /rawhtml >}}

For this to be a non-Markov evolution it would seem that there are two ways, $\gamma(t)>0$ or that $2\gamma(t)+\tilde\gamma(t)<0$. However, when taken to its canonical form the equation can be rewritten as
$$
\dot\rho=[\gamma(t)+\tilde\gamma(t)][2\sigma_x\rho\sigma_x+2\sigma_y\rho\sigma_y-4\rho]
$$
and we see that in reality only with one condition could it be non-Markovian, that being $\gamma(t)+\tilde\gamma(t)<0$. Another case in which one can see the need to take things to their canonical form is considering the following master equation
$$
    \dot\rho=L\rho L^\dagger-\frac{1}{2}(L^\dagger L\rho+\rho L\dagger L)-[L^\dagger\rho L-\frac{1}{2}(LL^\dagger\rho+\rho L L^\dagger)]
$$
where at first glance it seems to generate a non-Markov evolution. However, if we choose $L=(1+iH/\hbar)/\sqrt{2}$ we end up with a master equation of the form
$$
\dot\rho=-\frac{i}{\hbar}[H,\rho]
$$
which corresponds to a Markovian evolution.
\par We now move on to mention some measures of non-Markovianity based on the sign accompanying the decoherence rate at some given time. To describe non-Markovianity in an individual channel we use
$$
f_k(t):=max[0,-\gamma(t)]\geq 0.
$$
Or for a time $t$ without considering individual channels
$$
f(t)=\sum_{k=1}^{d^2-1}f_k(t)=\frac{1}{2}\sum_{k=1}^{d^2-1}\big[|\gamma_k(t)|-\gamma_k(t)\big]
$$
, if we extend this expression but for a time range we would have the expression

$$
F_k(t,t')=\int_t^{t'}ds f_k(s)
$$

which characterizes \emph{the total amount of non-Markovianness on channel $k$ over time step $[t,t']$}. We can also define a discrete measure as the number of strictly negative decoherence rates

$$
n(t):= \\# \\{ k: \gamma_k (t) < 0   \\} = \\# \\{ k:f_k(t) >0 \\}
$$

we call it _the non-Markov index_. To exemplify the use of these measures we take the case of a single decoherence channel. We consider the following master equation $\dot\rho=-\frac{i}{\hbar}[K(t),\rho]+\alpha(t)[A(t)\rho A(t)^\dagger-\frac{1}{2}\{A(t)^\dagger A(t),\rho\}]$. Its canonical form will be
$$
\dot\rho=-\frac{i}{\hbar}[H(t),\rho]+\gamma(t)[L(t)\rho L(t)^\dagger-\frac{1}{2}\{L(t)^\dagger L(t),\rho\}]
$$
By the definition of non-Markovianity, the evolution of the system is non-Markovian, at time $t$ if and only if $\gamma(t)<0$. The total amount of non-Markovianity would be calculated as
$$
F(t,t')=-\int_{\gamma(t)<0}ds\gamma(s)
$$
Furthermore, the discrete non-Markov index would be unity when $\gamma(t)<0$ or zero otherwise.

**Distance measures:** A measure for the non-Markovianity of quantum dynamics of open systems is constructed based on the trace distance of two quantum states which describes the probability of successfully distinguishing these states. The basic idea underlying this construction is that Markovian processes tend to continuously reduce the distinguishability between any two states, while the essential property of non-Markovian behavior is the growth of this distinguishability. The loss of distinguishability of states is interpreted as an information flow from the open system to its environment.\\
To construct the measure for non-Markovianity we need a measure for the distance between two quantum states $\rho_1$ and $\rho_2$. Such a measure is given by the trace distance which is defined as
$$
D(\rho_1,\rho_2)=\frac{1}{2}Tr|\rho_1-\rho_2|
$$
where $|A|=\sqrt{A^\dagger A}$. A property that we should note is that all trace-preserving and completely positive maps $\Phi$ are contractions for this metric.
$$
D(\Phi_{\rho_1},\Phi_{\rho_2})\leq D(\rho_1,\rho_2)
$$
This means that no trace-preserving quantum operation can ever increase the distinguishability of two states.
\par Suppose we have a quantum process given by a Markovian master equation,
$$
\frac{d}{dt}\rho(t)=\mathcal{L}\rho(t),
$$
with $\mathcal{L}\rho=-i[H,\rho]+\sum_i\gamma_i\Big[A_i\rho A_i\dagger-\frac{1}{2}\{A_i\dagger A_i,\rho\}\Big]$ involving positive relaxation rates $\gamma_i\geq 0$. Such a master equation leads to dynamical maps $\Phi(t)=exp(\mathcal{L}t)$, $t\geq0$, which describes the dynamics of the density matrix through the relation $\rho(t)=\Phi(\tau)\rho(0)$. It can be shown that
$$
D(\rho_1(\tau+t),\rho_2(\tau+t))\leq D(\rho_1(t),\rho_2(t))
$$
where $\rho_{1,2}(t)=\Phi(t)\rho_{1,2}(0)$. Hence, the trace distance of states $\rho_{1,2}(t)$, with any initial state $\rho_{1,2}(0)$, is a monotonically decreasing function of time. The interpretation of this is that this is a feature of quantum Markovian processes, implying that under Markovian evolution any two states generally become less and less distinguishable as time increases. Furthermore, it can be proven that the inequality given above holds for every time-dependent Markovian process defined by the master equation with $\gamma_i(t)\geq 0$.
\par We define the rate of change of the trace distance with
$$
\sigma(t,\rho_{1,2}(0)) = \frac{d}{dt}D(\rho_1(t),\rho_2(t)).
$$
There are many processes for which $\sigma$ is greater than zero for certain times. It is such processes that we define as \emph{non-Markovian}. We then complement the definition given above for non-Markov processes by now saying that a process is non-Markovian if there exists a pair of initial states $\rho_{1,2}(0)$ and a certain time $t$ such that $\sigma(t,\rho_{1,2}(0))>0$.

We take the case for one qubit to exemplify this case.
Given a single-qubit density matrix $\rho$, since Pauli matrices form a basis for $2\times2$ complex matrices, the Bloch sphere representation can be given as:
$$\rho = I + \vec{r} \cdot \vec{\sigma}$$

where $\vec{r} = (r_x, r_y, r_z)$ and $|\vec{r}| \leq 1$.

The expectation values ​​of the Pauli matrices $\sigma_x$, $\sigma_y$ and $\sigma_z$ can be calculated from the density matrix $\rho$ as follows:

$$r_x = Tr(\rho \sigma_x);\quad r_y = Tr(\rho \sigma_y); \quad r_z = Tr(\rho \sigma_z)$$

where $Tr$ denotes the trace operation. The trace distance between two qubits in the Bloch representation is equal to half the Euclidean distance between their Bloch vectors. For example, suppose we have two qubits with Bloch vectors $\vec{r_1}$ and $\vec{r_2}$. The Euclidean distance between these vectors is given by:

$$d(\vec{r_1}, \vec{r_2}) = \sqrt{(r_{1x} - r_{2x})^2 + (r_{1y} - r_{2y})^2 + (r_{1z} - r_{2z})^2}$$

The trace distance between these qubits is then: $D(\rho_1, \rho_2) = \frac{1}{2} d(\vec{r_1}, \vec{r_2})$. The master equation for a qubit in the Bloch representation is given by:
$$\frac{d}{dt} \rho = -i [\mathcal{H}, \rho] + \mathcal{L}(\rho)$$
where $\rho$ is the density matrix of the qubit, $\mathcal{H}$ is the Hamiltonian of the system, and $\mathcal{L}(\rho)$ is the Lindblad superoperator describing the dissipative dynamics of the system.

The Bloch vector is a representation of a qubit state that is commonly used in quantum mechanics. The Bloch vector is related to the density matrix of a qubit state by:

$$\vec{r} = \text{Tr}(\rho \vec{\sigma})$$

where $\rho$ is the density matrix of the qubit state and $\vec{\sigma}$ is a vector containing the three Pauli matrices. The master equation for a qubit in the Bloch representation can be derived from the master equation for a qubit in the density matrix representation using the relationship between the Bloch vector and the density matrix.

$$\rho = \frac{1}{2}(I + \vec{r} \cdot \vec{\sigma})$$
The master equation for a qubit in the Bloch representation can be written as:

$$\frac{d}{dt} \vec{r} = \vec{u} + D \vec{r}$$

where $\vec{r}$ is the Bloch vector of the qubit state, $\vec{u}$ is the drift vector, and $D$ is the damping matrix. The drift vector $\vec{u}$ and the damping matrix $D$ depend on the specific physical system under consideration. In general, the drift vector $\vec{u}$ describes the coherent evolution of the qubit state, while the damping matrix $D$ describes the incoherent evolution of the qubit state due to ambient noise.
The drift vector $u_j$ is defined as $(1/2)Tr[\sigma_j\Lambda(1)]$ and the damping matrix $D_{jk}$ is defined as $(1/2)Tr[\sigma_j\Lambda(\sigma_k)]$ . The Bloch equation can be written as $\dot v = u+Dv$ where v is the Bloch vector.

$$
u_j = \frac{1}{2}tr[\sigma_j\Lambda(1)];\quad
D_{jk} = \frac{1}{2}tr[\sigma_j\Lambda(\sigma_k)];\quad
\frac{dv}{dt} = u + Dv
$$

The trace distance of any two density operators, $\rho$ and $\rho+\delta\rho$, is
$$
(\delta s_{Tr})^2:=\frac{1}{4}(Tr|\delta\rho|)^2=\frac{1}{4}\delta \textbf{x}.\delta \textbf{x}
$$
We want to see what happens when two density matrices differ by a $\delta\rho$ so considering the master equation in the Bloch representation for a Bloch vector we get that $\delta \dot x=D\delta x$, and therefore

$$
\frac{d}{dt}((\delta s_{Tr})^2
)=\frac{1}{4}[\delta\dot x.\delta x+\delta x.\delta\dot x]=\frac{1}{4}\delta x^{T}(D+D{T})\delta x
$$
From that equation we see that the trace between a pair of density operators increases if and only if it can increase between a pair of infinitesimally separated states. But, the equation also tells us that it can increase if and only if the matrix $D+D^T$ has positive eigenvalues. That is, \emph{The trace distance of the qubit can precensus non-Markovianity at time $t$ if and only if the damping matrix satisfies the condition}
$$
\lambda_{\text{max}}[D(t)+D^T(t)]>0
$$
where $\lambda_{\text{max}}(A)$ denotes the maximum eigenvalue of $A$.

# Conclusion
The canonical form of the master equation gives us the mathematical form necessary to be able to evaluate the non-Markovianity of a given system. Such a canonical form leaves us with uniquely determined decoherence rates. We arrive at a positive (negative) canonical decoherence rate corresponding to a Markovian (non-Markovian) evolution. This led us to define the non-Markovianity measure called trace distance which tells us what kind of evolution is going on based on the rate of change of the trace distance. Also, for each of these steps to characterize the non-Markovianity of the system we saw some examples. First, how bringing the system to its canonical form was crucial for the characterization. Second, the case of a single-channel system as a test. Finally, third, we dealt with the case of the one-qubit master equation in its Bloch representation. The above results demonstrate the value of digging deeper into aspects of the non-Markovian evolution characterization. Finally, it would also be interesting to explore the experimental aspects related to the concepts touched on in the text.

# References
[1] G. Lindblad, Comm. Math. Phys. 48, 119 (1976)

[2] M.J.W. Hall, J.D. Cresser, L. Li and E. Andersson, “Canonical form of master equations and characterization of non-Markovianity,” Phys. Rev. A 89, 042120 (2014).
    
[3] H.-P. Breuer, E.-M. Laine, and J. Piilo, “Measure for the Degree of Non-Markovian Behavior of Quantum Processes in Open Systems,” Phys. Rev. Lett. 103, 210401 (2009)

# Citation

Cited as:
> Takagui-Perez, R. Kenyi. How to measure the non-Markovianity of a Quantum System? Kenyi'Log.  
> https://taogenna.github.io/kenyi-blog/docs/oqs/oqs/

Or


```
@article{something,
  title   = "How to measure the non-Markovianity of a Quantum System?",
  author  = "Takagui-Perez, R. Kenyi",
  journal = "https://taogenna.github.io/kenyi-blog/",
  year    = "2024",
  month   = "Dec",
  url     = "https://taogenna.github.io/kenyi-blog/docs/oqs/oqs/"
}