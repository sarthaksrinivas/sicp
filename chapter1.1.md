# Chapter 1
## 1.1 Elements of Programming
* programming language = framework for organizing ideas about processes
### 1.1.1 Expressions
* how to combine simple ideas into complex ones
    1. primitive expressions: atoms
    2. means of combination: building compound expressions
    3. means of abstraction: simplifying compound expressions (through define)
* expression: a combination of primitive data (i.e. what is already known like atoms)
* evaluation: process of simplifying, understanding, and doing *something* with expressions
* combination
    * expressions that indicate procedure application
    * in scheme: enclosing expressions in parantheses
    * combination: (operator operand operand ...)
* argument: value of operand
* value/result of combination
    * applying operator/procedure to arguments
* prefix notation: placing operator to left of operands
    * unambiguous
    * allows nesting: combinations whose elements are themselves combinations
* use pretty printing to avoid confusion
* read–eval–print loop (REPL)
    * read stdin, evaluate expression, print result
## 1.1.2 Naming and Environment
* variable: means provided by programming language to name elements
    * value of variable = element
* in scheme variable definition: (define variable value)
* encourages incremental development and testing
* global environment: memory program keeps to remember variable–value pairs
 
### Exercise 1.1
``` lisp
10
12
8
3
6
a
b
19
#f
4
16
6
16
```

### Exercise 1.2
``` lisp
(/ (+ 5
      4
      (- 2
         (- 3
            (+ 6
               (/ 4 5)))))
   (* 3
      (- 6 2)
      (- 2 7)))
```

# Exercise 1.3
```
; My solution
(define (sum-of-squares a b c)
    (+ (expt (max a b c) 2)
       (expt (min (max a b) (max b c) (max a c)) 2)))

; Simplest solution
(define (square x) (* x x))
(define (sum-of-squares a b c)
    (+ (square (max x y))
       (square (max (min x y)
                    z))))
```

# Exercise 1.4
if b is positive, return + procedure to apply to a and b.
if b is negative, return - procedure to apply to a and b.
resulting function is a + abs(b)

# Exercise 1.5
with applicative–order evaluation, the interpreter will be stuck in an infinite loop.
with normal–order evaluation, the interpreter will print 1.
this happens because applicative–order evaluation needs to evaluate all subexpressions before it can print an answer. if a subexpression evaluates to an infinite loop, the interpreter will hang. in normal-order evaluation, the same subexpression won't evaluate at all if it doesn't need to be evaluated to yield an answer (here, it is an optional else clause).
