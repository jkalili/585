# Homework 1

### Adrian Leung, Nick Morgan, Jason Kalili

<br>

## Problem Set

<ol>
<br><li><h3>On the course notes page entitled “The Study of Programming Languages” we saw a function written in several programming languages. Write this function in a language not on this list. Prove that your function works on a tio.run or replit.com page. Include the link to your code in your answer.</h3>

```julia
function add(x)
  sum = 0
  for element in x
	  if element % 2 == 0
	    sum += element * element
	  end
  end
  sum
end
```

<li><h3>In your own words, write one sentence for each of the four major theories of computation, conveying its central question and its areas of concern. Write as if your job depended on clarity, accuracy, and solid English writing skills.</h3>

<p><u>Language Theory:</u> Theorizes how all computations are expressed and information is represented as strings of symbols from a finite alphabet to convey some meaning.</p>
<p><u>Automata Theory:</u> The study of machines, or automata, and how their limited features can be used to solve problems.</p>
<p><u>Computability Theory:</u> Fundamentally speaking, what are the limits of computation, and how does computability pertain to a function on the natural numbers?</p>
<p><u>Complexity Theory:</u> Theorizes the practical time and space resources required so run a computation or solve a problem</p>

<h3><li>In the Theories of Computer Science lecture we saw how to express the odd-number test in Lambda Calculus notation, Lisp, Python, JavaScript, Java, Ruby, Clojure, and Swift. Show how, in each of these notations or languages, to express a function to cube a number. (Research may be required.)</h3>

Lisp

```Lisp
(LAMBDA (x) (expt x 3))
```

Python

```Python
lambda x: x**3
```

Javascript

```JavaScript
x => x**3
```

Java

```Java
x -> x*x*x
```

Ruby

```Ruby
->(x) {x**3}
```

Clojure

```Clojure
#(* %1 (* %1 %1))
```

Swift

```Swift
{(x:Int) -> Int in return(x*x*x)}
```

<br><li><h3>Mark each of the following as true or false:

<ol style = 'list-style-type: lower-latin;'>
    <li>∅∈∅ <u>False</u>
    <li>∅∈{∅} <u>True</u>
    <li>∅⊆∅ <u>True</u>
    <li>∅⊆{∅} <u>True</u>
    <li>{x,y}⊆P({x,y,{x,y}}) <u>True</u>
    <li>P(∅)={∅} <u>True</u>
    <li>{x,y,z}3−{s∣|s|≤3}≠∅ <u>COME BACK TO THIS</u>
    <li>⋃{N,B,Q}−B=Q <u>True*</u>
    <li>(9,3,F)∈Z×B×R∧(1,2)↓1=2 <u>True</u>
    <li>|P({a,b,c})−P({a,b})|=5 <u>False</u>
</ol>
</h3>
<br><li><h3>Is the intersection of two partial orders a partial order? If so, prove it. If not, give a counterexample.</h3>
<p>The interesection of two partial order is</p>

https://math.stackexchange.com/questions/2057729/prove-or-disprove-if-r-and-s-are-partial-order-relations-on-a-set-a-then-r-c

<li><h3>Let f=λx.2x+1 and g=λx.λy.3xy. Reduce each of the following expressions (or if they cannot be reduced, say why):
<ol style = 'list-style-type: lower-latin;'>
    <li>f5(20) => 671
    <li>f∘f => 4x+3
    <li>g(f[5/3](3)−f[5/3](2))
    <li>(λw.(f−1(71),w(5),w(1)))(f∘(g1))
    <li>(λx.(xx))(λx.(xx))
</ol>

<br><li>Give exact answers to each of the following:

<ol style = 'list-style-type: lower-latin;'>
    <li>3↑↑2 => 27
    <li>2↑↑↑3 => 65536
    <li>7909128533892359mod90277 => 14941
    <li>(3+2i−8k)×(8i+2j−k)       (quaternion multiplication)
    <li>log82333333333
</ol>

<br><li>Translate the following sentences into logical notation.

<ol style = 'list-style-type: lower-latin;'>
    <li>If you don't leave now, you will not win the prize.
    <li>Ani or her sisters might have been late.
    <li>Some dogs like cats who live in the capital of Turkey.
    <li>The person who won the race prefers orange juice to tea.
    <li>3 will never be greater be 7.
    <li>Not every odd number is greater than its own square.
    <li>Something evil caused all evil things except itself.
    <li>Some day, it will be possible that all players will have the same score.
    <li>War is peace, freedom is slavery, and ignorance is strength.
    <li>All that was once true will someday necessarily be forever false.
</ol>

<br><li>In classical logic, ∃ and ∀ are duals of each other, because (¬∃x.P)≡∀x.¬P and (¬∀x.P)≡∃x.¬P. Are the temporal operators F and G duals of each other? Why or why not?

<p>This is like the </p>

<li>Suppose that you had a classical, bivalent logistic system powerful enough to express statements about the provability of its own formulas, for example, “This formula is not provable” or equivalently “I am not provable.” Show that such a system, if consistent, must be incomplete, and if complete, must be inconsistent.

<p>This is the </p>

</ol>
