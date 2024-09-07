# CLooG

CLooG is a free software and library to generate code for scanning Z-polyhedra. That is, it finds a  code (e.g. in C, FORTRAN...) that reaches each integral point of one or more parameterized polyhedra. CLooG has been  originally written to solve the code generation problem for optimizing compilers based on the polytope model.  Nevertheless it is used now in various area e.g. to build control automata for high-level synthesis or to find the  best polynomial approximation of a function. CLooG may help in any situation where scanning polyhedra matters. While  the user has full control on generated code quality, CLooG is designed to avoid control overhead and to produce a  very effective code.

*homepage*: <http://www.bastoul.net/cloog/index.php>

version | toolchain
--------|----------
``0.18.1`` | ``GCC/4.8.2``
