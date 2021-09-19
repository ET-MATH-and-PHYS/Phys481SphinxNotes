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
-----------------------------------------------------------


Due to issues of rounding and computer representation of floating point numbers, equality should never be used to compare floating points and instaed the magnitude of the difference should be compared against some tolerance; for example :math:`1E-6` (single precision) or :math:`1E-15` (double precision).

For conversions to different bases in python, we have the functions int(), bin(), oct(), and hex(). We can also use the format() function to change between bases, in particular using "{:#}" before other formatting terms. For example, {:#d} gives decimal, {:#b} gives binary, {:#o} gives octal, and {:#x} is hexidecimal.

For integer representation, a byte consists of 8 bits, and :math:`n` bytes can contain any number from :math:`0` to :math:`2^{8\cdot n}`. To denote the sign we add a sign bit out from, with :math:`0` indicating :math:`+` and :math:`1` for :math:`-`. We can also use scientific notation, using some of the bits for the exponent, and some for the mantissa. Single precision floating points use 32 bits: 1 for the sign, 8 for the exponent, and 23 for the mantissa (+1 which is implicit).









.. figure:: /Images/Logo.png
   :align: right
   :scale: 30 %
  

