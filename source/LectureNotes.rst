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


.. figure:: /Images/Logo.png
   :align: right
   :scale: 30 %
   
