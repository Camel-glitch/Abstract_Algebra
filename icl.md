### Introduction to Internal Composition Laws (ICL)
Here is an equation:

$$
E = mc^2
$$

**Real-life examples:**
* Mixing two colors.
* Concatenating two strings.
* Opening your fridge, then taking something in it (combined action).
* Composing functions (similar to a combined action).

> **Object-Action duality:** You can view the elements of $E$ as actions and the law as the combining action. For example, when calculating $2 + 3$, you can see $2$ as the action of adding two apples to a box. By combining these two actions, you obtain the action of adding five apples to a box. So, you apply an action to modify an object or a state. 
> 
> Alternatively, you can see $2 + 3 = 5$ as an object equation where you do nothing—you only describe that if you have one box with $2$ apples and one with $3$, then you have $5$ apples.

**Definition:** A ICL is defined as $$* : E \times E \to E$$, it can simply seen as a composition operator. 

**Why is it useful?**
Having this closure property makes software robust. We can compute as much as we want and never output an unexpected type.

---

### Key Elements & Properties

#### Absorbant Element
**Definition:** $$x * a = x \text{ for all } a$$

**IRL examples:**
* Mixing black color with any other color gives black (approximate, if you aren't a painter!).
* Multiplying anything by zero gives zero.
* *Note:* There is no absorbant element for concatenating two strings.

#### Cancellable Element
You can visualize this dynamically. If you transform two different things using the same transformation and obtain the same final result, then the transformation is **not** cancellable. 
It *is* cancellable if obtaining the same final result guarantees that the initial states were identical.

**IRL examples:**
* Doing nothing in composing functions.

#### $n$-th Iterate
Because you have an ICL, you can mix blue with blue, and mix blue again, etc., or concatenate the same string multiple times.

**Notation:** $x^n$

#### Idempotent Element
Sometimes you don't need to repeat something; just do it one time. 

**Definition:**
$$x * x = x$$

**IRL examples:**
* Mixing blue with blue gives blue. *(Remark: All colors are idempotent, wouhou!)*

#### Commutativity
This applies when you don't care about the order in which you do things. Doing $y$ then $x$ is the exact same as doing $x$ then $y$.

**Definition:**
$$x * y = y * x$$

**IRL examples:**
* Mixing blue and red is the same as mixing red and blue.
* Concatenating "Hello" to "World" is **not** the same as concatenating "World" to "Hello".

#### Associativity
Associativity means it is the same to combine $A$ with $B$ and then with $C$, as it is to combine $A$ with the result of combining $B$ and $C$. 

If you have an "and then" operation, it is the same as having an associative operation:
* **"And then" operation:** You have a starting state $s$ and actions $a$ and $b$. Doing $a$ "and then" $b$ means applying $a$ to $s$, and then applying $b$ to the result. 
* $s(a \mathbin{\&} b) = (sa)b$, where $\&$ is an associative operation. All associative operations are "and then" operations.
* **Conclusion:** Associative operations mean there are "and then" operations.

**IRL examples:**
* The order of matrix multiplication can be crucial for time complexity: $(np \times pm) \times mq = \mathcal{O}(mn(p+q))$ versus $np \times (pm \times mq) = \mathcal{O}(pq(m+n))$.
* Addition in Python of floating points is not strictly associative. By grouping one way you avoid computing errors, and with the other, you might introduce them.
* NAND and NOR gates are commutative ICLs that are **not** associative.

#### Power Rule
Using associativity, you can establish power rules:
* $x^n * x^p = x^{n+p}$
* $(x^n)^p = x^{np}$

---

### Transformations

#### Doing Nothing Transformation (Identity/Neutral Element)
Some sets have a "doing nothing" transformation, which is unique.

**Definition:**
$$x * e = e * x = x$$

#### Reversible Transformation (Inverses)
Some transformations are reversible. If you apply $x$ and can then undo the effect of $x$ using another transformation, then $x$ is reversible. 
* Undoing a transformation means that the net result is doing nothing.
* $x * y = e$ (where $y$ is called the inverse of $x$).
* An absorbant element is **never** reversible.
* If the law is associative, the inverse is unique.

Some transformations invert themselves. For example, rotating by $\pi$ and then doing it again is like doing nothing. Alternatively, applying the exact same transformation multiple times might be like doing nothing. The **order** of a transformation is the minimum number of times you have to apply it to undo the effect (e.g., rotating by 30 degrees requires 12 iterations to undo the effect).

**Order notation:**
$$\min \{ k \mid x^k = e \}$$

#### Reversible Transformation Properties
If your law is associative, inverses have specific properties:

**Shoes and Socks Property:**
If $x$ and $y$ are invertible, then doing $x$ and then $y$ is also invertible. You simply undo the last transformation ($y$) and then the first ($x$):
$$(xy)^{-1} = y^{-1} x^{-1}$$

**Negative Powers:**
You can invert the $x^n$ transformation by undoing $x$ a total of $n$ times. By definition, we denote this as a negative power:
$$(x^n)^{-1} = (x^{-1})^n = x^{-n}$$

**Commutating Transformations:**
Commutative transformations act in parallel; they are like independent variables. For example, putting on a hat and putting on socks are commutative actions, but putting on shoes and socks are not. 

If $x$ commutes with $y$, then $x^{-1}$ also commutes with $y$. This makes sense because the inverse transformation acts on the same locality as $x$ (e.g., undoing socks means pulling off socks, which doesn't modify the state where $y$ acts). 
* All powers of $x$ and $y$ follow the same rule. 
* If $x$ and $y$ commute: $(xy)^n = x^n y^n$.
