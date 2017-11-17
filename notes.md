# Haskell programming from First principles

## Haskell and functional programming

* Haskell is purely functional because it does not have any features
  that cannot be translated into lambda expressions.
* The word "purity" is also used to refer to "referential purity" in
  functional programming. It means the same function, given the same
value to evaluate, will always return the same result.
* Function:It is a relation between a set of possible inputs and a set of
  possible outputs.

* Lambda calculus has three basic components(lambda terms):
    - Variables - names for potential inputs
    - Abstractions: a function. It has a head(a lambda) and a body. The
      head is a lambda follwed by a variable name. This variable is a
parameter and binds all instances of that same variable in the body.
Lambda abstraction is an anonymous function. eg : lambda x. x
    - Expressions: a variable, an abstraction, or a combination of both

* Aplha equivalence: The x in the abstraction above has not semantic
  meaning except in its role in that expression. So there is a form of
equivalence between lambda terms called alpha equivalence. That is,
    lambda x.x
    lambda y.y
    lambda z.z
                all mean the same thing.

* Beta reduction: When we apply a function to an argument, we substitute
  the input expression for all the instances of bound variables and we
eliminate the head since its only purpose was to bind the variables. The
process of beta resuction ends when there are no more lambdas left.

* Left associative: The applications in the lambda calculus are left
  associative. That is unless explicitly specified using paranthesis,
they group to the left. so,
        (lambda x.x)(lambda y.y)z
    := ((lambda x.x)(lambda y.y))z
    := (lambda y.y)z
    := z

* Free variables: The variables that are not named in the head. Alpha
  equivalence does not apply to free variables.

* Only one parameter: Each lambda can only bind one parameter and can
  only accept one argument. So functions that need multiple argument
have nested heads. During beta application of such functions, the
leftmost heads keep getting eliminated. This is called currying. For
example, lambda xy.xy is a shorthand for lambda x.(lambda y.xy)

* Examples examples, (lambda xy.xxy)(lambda x.xy)(lambda x.xz)
    Substitution is a mess because of all these x's. But there are all
different x's because each bound by a different head.
    #TODO Is is why data constructors and type constructors can have the
same name because they have different namespaces??

