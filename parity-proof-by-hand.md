Parity proof
=============

Consider a point in time after publishing Xors of DH secret pairs. The attacker
knows following list of expressions:

    exprs = [xor([esk[ii], esk[ii+1 % group_size]]) for ii in range(1, group_size + 1)]

where we are counting from 0. We assume every `esk[ii]` is unique and fresh, and
is nonzero.

From these pairs, the attacker can only construct expressions with even numbered
terms, before simplification. After simplification, the expressions must still
be even numbered. That is because we can only cancel terms two at a time,
meaning the even-ness is invariant. Therefore the attacker cannot derive any
single esk. They need all the esks to construct the gkey.


[^xor-details]: Note that I the xor function in the expression actually xors
together lists, similarly to the sum function in Python.
