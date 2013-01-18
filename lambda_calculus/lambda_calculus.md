The Lambda Calculus
===============================================================================
The Lambda Calculus is a mathematical theory of computation that is equivalent
to Turing's model for computable functions.  It is based on the manipulation of
_lambda expressions_, which are formally defined as a combination of the 
following things (where A, B, and C are arbitrary &lambda;-expressions):

>  _name_ or   &lambda; _name_ . A or   (&lambda;x.B C)

The _name_ represents a unary function (i.e. a function with one argument) that 
has no side effects.

The second form is called abstraction; &lambda;x.A binds all occurences of x 
in the (arbitrary) lambda expression A; It is equivalent to using x as the 
parameter of a function in a modern computer language.

The third form is application of &lambda;-expression 1 to &lambda;-expression 2;
(&lambda;x.B C) has the effect of replacing all occurences of x in B with C.

Some Examples
** &lambda;x.x **
[Markdown syntax](http://daringfireball.net/projects/markdown/dingus)
