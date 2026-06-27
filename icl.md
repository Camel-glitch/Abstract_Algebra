Real life example :   
- Mixing two colours
- Concatenate two strings
- Open your fridge then take something in it (combine action)
- Composing functions (similar to combine action)

Def : $ * : ExE -> E $ 

Why it is useful ?  
Having this closure property make software robust, we can compute as much as we want and never output some unexpected type.
 

Absorbant element :  
- Mixing black colour with any other colour give black (I'm not a painter, I approximate).  
- Multiply anything by zero give zero. 
- No for concatenating two strings 

Def : $  x*a = x for all a $

Cancellable element : 
We can see it dynamically
You transform two different thing using the same transformation and you obtain the same final thing then the transformation is not cancellable. 
It's cancellable if obtaining the same final thing, tell you that the initial state are the same.   

IRL examples :  
- Doing nothing in composing function. 


nth Iterate:
As you have an icl you can mix blue with blue and mix blue etc. or concatenate the same string multiple times. 
Notation : $x^n$

Idempotent element : 
Sometimes you don't need to repeat something, just do it one time. 
$x*x \eq x$   

IRL example :  
- Mixing blue with blue give blue. Rk: All the colours are idempotent wouhou! 

Comutativity :
If you don't care about the order you do thing.  
Doing y then x is the same as doing x then y $x*y \eq y*x$

IRL : 
- Mixing blue to red is the same as mixing red to blue 
- Concatenate "Hello" to "World" is not the same as concatening "World" to "Hello" 
