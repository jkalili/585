# Homework 2

### Adrian Leung, Nick Morgan, Jason Kalili

<br>

## Problem Set

<h3>1. Given L1={0,011,10} and L2={10,1}. What are:
<ol style = 'list-style-type: lower-latin;'>
    <li> L_1 ∪ L_2 <u>{0, 1, 10, 011}</u>
    <li> L_1 ∩ L_2 <u>{10}</u>
    <li> L_1L_2 <u>{010, 01, 01110, 0111, 1010, 101}</u>
    <li> L_2^∗ <u>{𝜀, 10, 1, 1010, 101, 110, 11, 101010, 10101, 10110, 1011, 11010, 1101, 1110, 111, ...}</u>
    <!-- L2 = {a,b} = {empty, a, b, aa, ab, ba, bb, aaa, aab, aba, abb, baa, bab, bba, bbb} -->
</ol>
</h3>

<h3>2. Characterize the following languages in set-theoretic notation:
<ol style = 'list-style-type: lower-latin;'>
    <li> Binary numerals in which 1s never appear together, but only with at least two 0s between them <u>{w ∈ {0, 1}* | 0*(100⁺)*0*}</u>
    <li>The language of Pythagorean triples, written as decimal numerals, where the three values are separated by commas<u>{(x, y, x²+y²) | x,y,x²+y² ∈ ℕ ∧ (x>0 ∧ y>0)}</u>
    <li>All strings over the alphabet a,b,c,d,e where the symbols are in decreasing alphabetic order<u>{x ∈ {a,b,c,d,e} | a*b*c*d*e*} or {aʰbⁱcʲdᵏeˡ | h,i,j,k,l ≥ 0}</u>
</ol>
</h3>

<h3>3. Give grammars for the following, using the list-of-rules notation from class:
<ol style = 'list-style-type: lower-latin;'>
    <li> The empty language 
    ```
    s → "∅" | s
    ```
    <li> {0ⁱ1ʲ2ᵏ | i=j ∨ j=k}
    ```
    numeral → first
    first   → 0
    ```
    <!--
    𝜀, 01, 12, 012, 0011, 000111, 111222, 000111222
    -->
    <li>{w ∈ {0,1}* | w does not contain the substring 000}
    <li>{w ∈ {a,b}* | w has twice as many a's as b's}
    ```
    w      → before | after
    before → aa (before|after) b | 𝜀
    after  → b (before|after) aa | 𝜀
    ```
    <li>{aⁿbⁿaⁿbⁿ | n≥0}
    ```
    
    ```
    
</ol>
</h3>

<h3>4. Here’s another look at the grammar for floating-point numerals (using single-letter variables for compactness):</h3>

```Java
n = d+ f? e?
f = "." d+
e = ("E" | "e") ("+" | "-")? d+
d = "0" .. "9"
```

<h3>Give the (V,Σ,R,S)-definition of this grammar. (Note this means you will have to desugar the rules with |, ?, and +.)</h3>

<p>answer</p>

<h3>5. Give a programming langauge grammar, using the notation from class, for the programming language described as follows. Programs are made up of a possibly empty sequence of function declarations, followed by a single expression. Each function declaration is of the form f=(p1,…,pm)⇒e where f is the function name (an identifier), each pi is a parameter (also identifiers) and the result (the “body”) is an expression. Expressions can be numeric literals, string literals, identifiers, function calls, or can be made up of other expressions with the usual binary arithmetic operators (plus, minus, times, divide, remainder) and a unary prefix negation and a unary postfix factorial (!). There’s a conditional expression with the syntax x ? y : z. Parentheses are used, as in most other languages, to group subexpressions. Numeric literals are non-empty sequences of decimal digits with an optional fractional part and an optional exponent part. String literals delimited with double quotes with the escape sequences \', \", \n, \\, and \u{hhhhhh} where hhhhhh is a sequence of one-to-six hexadecimal digits. Identifiers are non-empty sequences of letters, decimal digits, underscores, and dollar signs, beginning with a letter or dollar sign. Function calls are formed with an identifier followed by a parenthesized, comma-separated list of expressions.</h3>

<p>The programming language</p>

<h3>6. For the language in the previous problem, write an abstract syntax specification </h3>

<p>picture here</p>

<h3>7. For the language in the previous problem, give an abstract syntax tree for the program:</h3>

```
gcd = (x, y) => y ? gcd(y, x % y) : x
cube = (x) => x * x * x
"The answer is" + cube(gcd(30, 4!)) + "😦😦"
```

<p>picture here</p>
