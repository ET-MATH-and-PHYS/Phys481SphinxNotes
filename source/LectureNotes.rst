.. _notes:

**Phys 481 Lecture Notes**
==========================


**Assignment 1 and the Cat Map (September 7th)**
------------------------------------------------

First we recall some basic container types in python, namely *lists* and *tuples*. Lists use the notation [...] in construction are are mutable, which is to say elements can be added or removed from a list after its creation. On the other hand, tuples use the notation (...) in construction and are immutable, so once created a tuple cannot have elements added or removed. Now, recall that two containers are determined to be **equal** in python if their corresponding elements are equal. Conversely, two containers are said to be **identical** in python if the variable names of the containers correspond to the same place in memory.


Now, Arnold's Cat Map is a special type of image transformation which acts on the coordinates of the pixels, and produces and shearing and folding effect. Further, in terms of matrix operations the cat map is given as follows, as depicted on the `wiki <https://en.wikipedia.org/wiki/Arnold%27s_cat_map>`_:

.. math::
    \Gamma:(x,y)\rightarrow (2x+y,x+y) \mod 1

which is to say the distorted pixels are returned to the 1 by 1 square in which they reside. Concretely, for an N by N array of pixels we write 

.. math::
    \Gamma': (i,j) \rightarrow (i+j, 2j+i) \mod N

where :math:`i` is the row and :math:`j` is the column, so as the column is associated with an x coordinate and the row is associated with a y coordinate the map is slightly reversed.

**Sphinx Setup (September 9th)**
--------------------------------

During this lecture sphinx was introduced and set up, so the primary information for this lecture day is found in :ref:`Sphinx Documentation <sphinxDoc>`.



**Shannon Entropy and Spamlet Assignment (September 14th)**
-----------------------------------------------------------


In basic probability theory, a random Bernoulli process consists of two outcomes, with probabilities :math:`p` and :math:`1-p`. In general, the sum of the probabilities of all possible outcomes for any experiment must be 1. The special case of a simple event in probability theory is that in which there are :math:`\Omega` outcomes, each of which has probability :math:`1/\Omega`.

Another important topic in computation theory is **Entropy** and *information*. Entropy can be thought of as a measure of the "surprise" factor of events associated with some data (for example a sequence). Shannon entropy quantifies this by defining entropy to the expected information content of a signal, calculated by 

.. math:: H = -\sum_{i=1}^np_i\log p_i

Often base 2 is used for the logarithm, giving the units of bits per symbol 

.. math:: H = -\sum_{i=1}^np_i\log_2 p_i = -\frac{1}{\ln 2}\sum_{i=1}^np_i\ln p_i

The entropy function has the following properties:
#. :math:`H(p_1,...,p_N)` is a concave function of :math:`p_i`.
#. for a given :math:`N`, the uniform distribution :math:`p_i = 1/N` has the maximum entropy :math:`H`
#. :math:`H(p_1,...,p_N)` is zero if and only if one of the :math:`p_i` is one (which is to say there is only one possible outcome)



**Numbers in Python (September 16th)**
--------------------------------------


Due to issues of rounding and computer representation of floating point numbers, equality should never be used to compare floating points and instaed the magnitude of the difference should be compared against some tolerance; for example :math:`1E-6` (single precision) or :math:`1E-15` (double precision).

For conversions to different bases in python, we have the functions int(), bin(), oct(), and hex(). We can also use the format() function to change between bases, in particular using "{:#}" before other formatting terms. For example, {:#d} gives decimal, {:#b} gives binary, {:#o} gives octal, and {:#x} is hexidecimal.

For integer representation, a byte consists of 8 bits, and :math:`n` bytes can contain any number from :math:`0` to :math:`2^{8\cdot n}`. To denote the sign we add a sign bit out from, with :math:`0` indicating :math:`+` and :math:`1` for :math:`-`. We can also use scientific notation, using some of the bits for the exponent, and some for the mantissa. Single precision floating points use 32 bits: 1 for the sign, 8 for the exponent, and 23 for the mantissa (+1 which is implicit).


**Computing Past Present and Future (September 21st)**
------------------------------------------------------

The history of computation was briefly touched on, including the effectiveness of mathematical models, famous computer errors, and computing progress along with the rate of growth.


**Report Writing (September 23rd)**
-----------------------------------

Requirements for assignments were discussed; importance of clear and effective documentation for functions, breaking up functions into smaller components, and writing proper introductions and conclusions.



**Automata and Life (September 28th)**
--------------------------------------


An automaton in terms of computers usually refers to a machine that performs a function according to a predetermined set of coded instructions, especially one capable of a range of programmed responses to different circumstances.

In the discussion of state in physics, we often refer to the **state** of a system as a complete description of the system. In particular, a complete state for a system provides all the possible information that can be observed about the system. 

All physical theories ultimately are based on three kinds of fundamental postulates:

#. Postulates which define the way we describe a state of a system
#. Postulates which specify what kind of information about observables, that is measurable properties of the system, is contained in the description of its state.
#. Postulates which provide us with laws that govern the time evolution of the system and allows us to predict its future state given the current one.



**Pseudo-Random Numbers (October 5th)**
---------------------------------------

A computer is a deterministic system so it cannot produce a truly random result, and instead is limited to pseudo-random number generators which use a deterministic algorithm for producing a sequence of seemingly random numbers. In general a PRNG consists of a function :math:`f` that operates on some number :math:`x_i` to produce a new number :math:`x_{i+1}` 

.. math:: x_{i+1} = f(x_i;a_1,a_2,...,a_n)

where :math:`a_n` are internal parameters specific to each implementation. A popular class of PRNGs are based on *multiplicative linear congruential generators* which are of the form 

.. math:: x_{i+1} = (ax_i+b) \mod m

In order to access the randomness of a PRNG it is important to analyze the generated numbers from multiple perspectives, such as graphically, plotting successive generated numbers on opposing axes in a 2d or 3d plot, and investigating hyperplanes. Looking at the entropy of the sequences of bits associated with generated numbers.




**Automata Entropy (October 7th)**
----------------------------------

It is important to consider the events or symbols chosen in analyzing entropy calculations, as they can lead to vastly different results. For instance, in analyzing the randomness of the evolution of a cellular automata for a given rule one can look at the entropy of a single cell from generation to generation, one can look at the entropy of a single cell for pairs of generations, or even triples, and one can even look at the entropy associated to a collection of cells.




**Boltzmann Distribution and Dipoles (October 12th)**
-----------------------------------------------------

For small systems in thermal equilibrium with some heat-bath at temperature T, the probability of the system being in a state :math:`\mathbf{x}` will follow a *Boltzmann distribution* which is of the form 

.. math:: p(\mathbf{x}) \propto \exp\left(-\frac{E(\mathbf{x})}{k_BT}\right)

where :math:`k_B` is the Boltzmann constant and :math:`E(\mathbf{x})` is the energy of the system for state :math:`\mathbf{x}`. A partition function is used for normalization of the probabilities associated to the various states. For the Boltzmann distribution the partition function is

.. math:: Z(T;E_j) = \sum_{j=1}^n\exp\left(-\frac{E_j}{k_BT}\right)

and it follows that for any :math:`j`, 

.. math:: p_j = \frac{1}{Z}\exp\left(-\frac{E_j}{k_BT}\right)

Further, it is conveniant in calculations to define :math:`\beta = \frac{1}{k_BT}`.

As a bit of python technology, the numpy.random.choice function is useful for obtaining an item from a list of symbols using another list which contains the probabilities for the various symbols. 

**Metropolis Algorithm (October 14th)**
---------------------------------------

The Metropolis-Hastings algorithm is a method based on Markov chains which uses equilibrium conditions to prove that, in our case, if the system of interest is in a state with energy :math:`E_0` and we flip the spin of a single random element so that the system now has energy :math:`E_1`, the probability of the system accepting this change would be 

.. math:: p = \min(1, \exp(-(E_1 - E_2)\beta))

In this case, the system will always move from a high energy state to a low energy state, and if the system is in a low energy state there is some probability that it will flip to a high energy state. THis probability increases with an increase in the temperature of the system.

When considering the energy of a system of magnetic dipoles in some external magnetic field, we must also take into consideration the small interactions between neighboring dipoles due to the magnetic fields generated by their respective magnetic moments. This can be done in a simple case for immediate neighbors with a week coupling 

.. math:: E_i = -JS_{i-1}S_i - JS_{i+1}S_i

where :math:`J` is a coupling constant.



**Ising Model (October 19th)**
------------------------------

In an Ising model we arrange dipoles in a square lattice, with periodic boundary conditions, such that each entry in the lattic contains the spin of the associated dipole. To a good approximation, when considering spin coupling between dipoles we need only consider the four adjacent dipoles. The energy of such a system without an external magnetic field is given by the Hamiltonian

.. math:: H = -J\sum_{i=1}^m\sum_{j=1}^n\sigma_{i,j}\left[\sigma_{i-1,j}+\sigma_{i+1,j}+\sigma_{i,j-1}+\sigma_{i,j+1}\right]

where :math:`\sigma_i` and :math:`\sigma_j` are states, and we are considering an :math:`m\times n` lattice of states, with periodic boundary conditions. 

For systems such as the one we are considering, there is a special temperature :math:`T_c` called the *critical* or *Curie temperature*, and at this temperature many thermodynamic phenomena occur, such as heat capacity having a peak. For the 2D Ising model it has been shown analytically that :math:`T_c` is 

.. math:: T_c = \frac{2}{\ln(1+\sqrt{2})}

Next, the *magnetization* for our system is the sum over all spins. Non-zero magnetizations generate magnetic fields. Often we are looking at the absolute value of the magnetization. Now, :math:`T_c` is also the temperature for which the magnetization goes to zero, and in general the system undergoes a phase transition. In particular, this is a second order or continuous transition which is for the transition between ferromagnetic and paramagnetic phases.




**Ising Model Continued (October 21th)**
----------------------------------------

When working with arrays of multiple dimensions, and in particular when going between programming languages, depending on the language operations may be done by rows or by columns, causing calculations to be slightly different. Thus, in testing it is advised to test with rectangular, non-square arrays to make sure the results you want occur, and that you are indexing the correct way. In particular, when graphing it's easier to see what is being done.


**Laplace's Equations (October 26th)**
--------------------------------------


Laplace's equation is a differential equation of the form

.. math:: \nabla^2\varphi = \frac{\partial^2\varphi}{\partial x^2} + \frac{\partial^2\varphi}{\partial y^2} + \frac{\partial^2\varphi}{\partial z^2} = 0

where :math:`\nabla^2` is the Laplace operator. It is an example of an elliptic PDE. Differential equations of this form appear often in the field of electrostatics as boundary value problems for electric potentials. In order to solve such an equation numerically one can use the method of finite differences which uses the Taylor expansion of a function :math:`f(x)` at a point :math:`a` to approximate its derivatives:

.. math:: \sum_{n=0}^{\infty}\frac{f^{(n)}(a)}{n!}(x-a)^n = f(a) + \frac{f'(a)}{1!}(x-a) + \frac{f''(a)}{2!}(x-a)^2+\frac{f'''(a)}{3!}(x-a)^3 + ...

Restricting to points evenly spaced by :math:`\Delta` we can obtain the form 

.. math:: f(x_{i+n}) = f(x_i) + f'(x_i)n\Delta + \frac{f''(x_i)}{2}(n\Delta)^2 + \frac{f'''(x_i)}{6}(n\Delta)^3+O(\Delta^4)


For adjacent points this becomes

.. math:: f(x_{i+1}) &= f(x_i) + f'(x_i)\Delta + \frac{f''(x_i)}{2}\Delta^2 + \frac{f'''(x_i)}{6}\Delta^3+O(\Delta^4)  \\
    f(x_i) &= f(x_i) \\
    f(x_{i-1}) &= f(x_i) - f'(x_i)\Delta + \frac{f''(x_i)}{2}\Delta^2 - \frac{f'''(x_i)}{6}\Delta^3+O(\Delta^4)

so subtracting two such neighbors gives

.. math:: f(x_{i+1}) - f(x_i) = f'(x_i)\Delta + \frac{f''(x_i)}{2}\Delta^2 + \frac{f'''(x_i)}{6}\Delta^3+O(\Delta^4)

From this we get our first estimate, the *forward difference estimate* of the first derivative:

.. math:: \frac{f(x_{i+1}) - f(x_i)}{\Delta} = f'(x_i) + \frac{f''(x_i)}{2}\Delta + \frac{f'''(x_i)}{6}\Delta^2+O(\Delta^3) \approx f'(x_i) + O(\Delta)

and similarly we can obtain the *backward difference estimate*, which together are 

.. math:: f'(x_i) &\approx \frac{f(x_{i+1}) - f(x_i)}{\Delta} + O(\Delta) \\
    f'(x_i) &\approx \frac{f(x_i) - f(x_{i-1})}{\Delta} + O(\Delta) 

We can also obtain the *first centered difference estimate* in a similar fashion

.. math:: f'(x_i) \approx \frac{f(x_{i+1}) - f(x_{i-1})}{2\Delta} + O(\Delta^2)

and the *second centered difference estimate*

.. math:: f''(x_i) \approx \frac{f(x_{i+1}) - 2f(x_i) + f(x_{i-1})}{\Delta^2} + O(\Delta^2)

One way to apply these estimates is to use the *relaxation method* which updates a grid of values iteratively using neighboring points and the finite differences method. However, this can take a long amount of time, and may not always yield the most accurate results.



**Physical Units (October 28th)**
---------------------------------

The scipy.constants package should be used whenever one is using physical constants in one's code. Also, when importanting it is recommended to only import the constants being used in the current project.

Often it is important to keep track of units in calculations. One package, of many, which does this is PINT with its UnitRegistry object. This allows one to add units to numbers in calculations, by multiplying by the unit registry object .(the appropraite unit), or simply call it with a string for the unit placed in. One can then perform dimensional analysis as an error will be thrown if mismatched units are added. Conversions can also be done with the variable.to() method, with the unit you wish to convert to placed in brackets. Unum is another python unit library.


**Laplace's Equations - Matrix Methods (Nov 2nd)**
--------------------------------------------------


Going back to the Laplace Equation, another method of applying the finite difference estimates is to use matrix applications, representing the 1 dimensional boundary value problem, for instance, as a system of equations with the finite difference equations applied to the Laplacian. This then takes the form of :math:`\mathbf{A}\vec{x} = \vec{b}`, where :math:`\vec{x}` is our desired array of potentials for our numerical solution, so the problem simplifies to solving the matrix equation. 

.. note:: 
    **Note**: In most applications it is much more efficient to solve a matrix equation rather than invert the matrix and multiply through the right hand side to get the solution. The result is also often more numerically stable. As grids get large the error in the numerical results can actually worsen as small errors accumulate over larger numbers of calculations. In this way solving is more stable than inverting, producing more accurate results even as grid sizes grow. 


Often in applications the system of linear equations that one is dealing with is *sparse*, which is to say that only a small portion of the matrix's entries are nonzero. Using specialized methods for these types of matrices can increase efficiency drastically, such as storing only the non-zero entries in memory. Specialized methods for storing and processing include Dictionary of Keys (DOK), List of Lists (LIL), Coordinate List (COO), Compressed Sparse Row (CSR or CRS), and Compressed Sparse Column (CSC or CCS).

scipy.sparse is a useful package for sparse matrix methods. scipy's linalg package also has a number of useful solving algorithms, as well as ones speciallized for sparse and banded matrices.




**Fourier Transforms and Audio Waves (Nov 4th)**
------------------------------------------------

In decoding audio signals the Fourier transform can be incredibly useful as it converts the signal from the time domain to the frequency domain, in which you can analyze the power of various frequencies in hopes of isolating your desired signal from any present noise. Often in this process visualizing the audio can be very useful, which is easily done using a *spectrogram*. In theory, when converted to the frequency domain white noise should be uniformly distributed with a relatively low power, while the actual signal will be more concentrated with a higher power, although this mainly holds for simple signals. 

One way of removing/reducing the noise is passing over to the frequency domain, applying a low-pass filter on the frequencies if you believe your actual signal is concentrated in a region of low frequencies, and then taking the inverse fourier transform to recover a denoised signal. Similarly, one can apply a high-pass filter if one believes that the signal contains mostly high frequency audio.

In numerical implementation, one often utilizes the *Fast Fourier Transform* for its speed and accuracy. It takes a sequence of numbers and returns a sequence of equal length after applying the transform. Note that both the input and output may be complex, but if the input is real the output will be symmetric about the vertical axis (0.0 frequency) with it equaling its complex conjugate.



**PDE Wave Equation (Nov 16th)**
--------------------------------

The one dimensional wave equation is given by 

.. math:: \frac{\partial^2u}{\partial t^2} = c^2\frac{\partial^2u}{\partial x^2},\;\;x \in (0,L),t \in (0,T]

where :math:`c` is a characteristic propagation speed. To fully specify this PDE we need two sets of initial conditions. Usually these take the form
.. math:: u(x,0) = I(x),\;\; x \in [0,L]

and 

.. math:: \frac{\partial}{\partial t}u(x,0) = V(x),\;\;x \in [0,L]

We may also specify spatial boundary conditions such as 

.. math:: u(0,t) &= 0,\;\;t \in (0,T] \\
    u(L,t) &= 0, \;\; t \in (0,T]

We use the method of finite differences to discretize this problem and obtain numerical solutions. The centered second differences estimates give

.. math:: \frac{u_i^{n+1} - u_i^n + u_i^{n-1}}{\Delta t^2} = c^2\frac{u_{i+1}^n - 2u_i^n + u_{i-1}^n}{\Delta x^2}

where :math:`u_i^n = u(x_i,t_n)`. We can use this to write 


.. math:: u_i^{n+1} = 2u_i^n - u_i^{n-1} + \frac{c^2\Delta t^2}{\Delta x^2}(u_{i+1}^n - 2u_i^n + u_{i-1}^n)

let :math:`C = \frac{c\Delta t}{\Delta x}`, and note that it is dimensionless. When :math:`C > 1` the largest effective numerical propagation speed is less than the physical speed, which can lead to inaccurate results. When the system is initially static :math:`V = 0`, 

.. math:: V = \frac{u_i^{n+1} - u_i^{n-1}}{2\Delta t} = 0
.. math:: u_i^{n+1} = u_i^{n-1}

so the first step doesn't require information about :math:`t < 0` 

.. math:: u_i^1 = u_i^0 - \frac{1}{2}C^2(u_{i+1}^0 - 2u_i^0 + u_{i-1}^0)

Solutions to the wave equation are conservative with energy at any given time being the sum of qaudratic terms: 

.. math:: E(t) := \frac{1}{2}\int_0^L[u_t^2(x,t) + c^2u_x^2(x,t)]dx

which correspond to the kinetic and potential energies respectively.

Standing waves arise from an initial condition

.. math:: u(x,0) = A\sin\left(\frac{\pi}{L}mx\right)

where :math:`m\in\mathbb{Z}` and :math:`A` is a freely chosen amplitude. The corresponding exact solution as a function of :math:`x` and :math:`t` is 

.. math:: u_e(x,t) = A\sin\left(\frac{\pi}{L}mx\right)\cos\left(\frac{\pi}{L}mct\right)





**Quadrature and Finite Differences (Nov 18th)**
------------------------------------------------

Recall that for a suitably nice function, :math:`f(x)`, we can expand its Taylor series as

.. math:: f(x+\Delta x) = f(x) + f'(x)\Delta x + \frac{f''(x)}{2}\Delta x^2 + \frac{f'''(x)}{3!}\Delta x^3 + ...

Using this we found the forward difference:

.. math:: f'(x) \approx \frac{f(x+\Delta x) - f(x)}{\Delta x}+O(\Delta x)

the backward difference:

.. math:: f'(x) \approx \frac{f(x)-f(x-\Delta x)}{\Delta x} + O(\Delta x)

and a centered difference:

.. math:: f'(x) \approx \frac{f(x+\Delta x) - f(x-\Delta x)}{2\Delta x} + O(\Delta x^2)





.. figure:: /Images/Logo.png
   :align: right
   :scale: 30 %
  

