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

Examples
--------
### Example 1 -- Identity
&lambda;x.x -- This is the identity operation; in Groovy, it would be `{ x -> x }`.

### Example 2 -- Self-apply
&lambda;s.(s s) -- Applies `s` to itself.  In Groovy `{ s -> s(s) }`

### Example 3 -- Boolean true and false
&lambda;first.&lambda;second.first --  This takes two arguments and returns the first.  ` {first, second -> first}`.  It is significant because Church used it as `true` in deriving boolean logic from the &lambda;-calculus.

&lambda;first.&lambda;second.second -- Return the second argument.  This is `false` in boolean logic.

### Example 4 -- if-then-else
&lambda;iftrue.&lambda;iffalse.&lambda;test.((test iftrue) iffalse)  -- If you apply this to a &lambda;-expression 
that evaluates to `true` or `false`, it becomes the standard if-then-else construct you find in 
almost every programming language.  In this case, the test is the third argument so you can curry it with iftrue and
iffalse expressions.  Thus 

>((&lambda;iftrue.&lambda;iffalse.&lambda;test.((test iftrue) iffalse) x) y) =>
(&lambda;iffalse.&lambda;test.((test x) iffalse) y) => 
&lambda;test.((test x) y)

The result is a function that you apply to a boolean condition.  

> &lambda;test.((test x) y) true => x
> &lambda;test.((test x) y) false => y

This is usually abbreviated to _&lambda;test.&lambda;iftrue.&lambda;.iffalse.(test iftrue iffalse)_

[Markdown syntax](http://daringfireball.net/projects/markdown/dingus)
