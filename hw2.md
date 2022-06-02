# Homework 2

### Adrian Leung, Nick Morgan, Jason Kalili

<br>

## Problem Set

<h3>1. Given L1={0,011,10} and L2={10,1}. What are:
<ol style = 'list-style-type: lower-latin;'>
    <li> L_1 ∪ L_2 <br><u>{0, 1, 10, 011}</u>
    <li> L_1 ∩ L_2 <br><u>{10}</u>
    <li> L_1L_2 <br><u>{010, 01, 01110, 0111, 1010, 101}</u>
    <li> L_2^∗ <br><u>{𝜀, 10, 1, 1010, 101, 110, 11, 101010, 10101, 10110, 1011, 11010, 1101, 1110, 111, ...}</u>
    <!-- L2 = {a,b} = {empty, a, b, aa, ab, ba, bb, aaa, aab, aba, abb, baa, bab, bba, bbb} -->
</ol>
</h3>

<h3>2. Characterize the following languages in set-theoretic notation:
<ol style = 'list-style-type: lower-latin;'>
    <li> Binary numerals in which 1s never appear together, but only with at least two 0s between them <br><u>{w ∈ {0, 1}* | w is a binary string in which 1s never appear together, but only with at least two 0s between them} or {w | 11 not in w and 101 not in w} (using python)</u>
    <li>The language of Pythagorean triples, written as decimal numerals, where the three values are separated by commas <br><u>{(x, y, z) | x²+y²=z² ∧ x,y,z ∈ ℕ}</u>
    <li>All strings over the alphabet a,b,c,d,e where the symbols are in decreasing alphabetic order <br><u>{aʰbⁱcʲdᵏeˡ | h,i,j,k,l ≥ 0}</u>
</ol>
</h3>

<h3>3. Give grammars for the following, using the list-of-rules notation from class:
<ol style = 'list-style-type: lower-latin;'>
<li> The empty language 
 
    s → s or there are no rules or (V,Σ,R,S) = ({s}, {a,b}, ∅, {s})
    
<li> {0ⁱ1ʲ2ᵏ | i=j ∨ j=k}

    s   → e01 "2"* | "0"* e12
    e01 → "0" e01 "1" | 𝜀
    e12 → "1" e12 "2" | 𝜀

<li>{w ∈ {0,1}* | w does not contain the substring 000}
    
    s -> char
    char -> "0" zero | "1" char
    zero -> "0" break | "1" char
    break -> "1" char | 𝜀

<li>{w ∈ {a,b}* | w has twice as many a's as b's}
    
    w      → before | after
    before → aa (before|after) b | 𝜀
    after  → b (before|after) aa | 𝜀

    w → z "aab" | "a" z "ab" | "aa" z "b" | "aab" z
      | z "aba" | "a" z "ba" | "ab" z "a" | "aba" z
      | z "baa" | "b" z "aa" | "ba" z "a" | "baa" z
    z → w | ε

<li>{aⁿbⁿaⁿbⁿ | n≥0}

    s      → l r
    l      → "a" l "b" x
    x "b"  → "b" x
    x r    → "a" r "b"
    x "a"  → "a" x
    l      → ε
    r      → ε

    Context Sensitive one

</ol>
</h3>

<h3>4. Here’s another look at the grammar for floating-point numerals (using single-letter variables for compactness):</h3>

```Java
n = d+ f? e?
f = "." d+
e = ("E" | "e") ("+" | "-")? d+
d = "0" .. "9"
```

    ({variables (vocab) set},
    {alphabet set},
    {rules set},n)

<h3>Give the (V,Σ,R,S)-definition of this grammar. (Note this means you will have to desugar the rules with |, ?, and +.)</h3>

```
*NOTE* -> replace variable e with c (since e is in the alphabet)
    ({n, f, c, d},
    {𝜀, ., E, e, +, -, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9},
    {
        (n, dfc),
        (f, .d),
        (f, 𝜀),
        (c, Ead),
        (c, ead),
        (a, +),
        (a, -),
        (a, 𝜀),
        (0d, d),
        (1d, d),
        (2d, d),
        (3d, d),
        (4d, d),
        (5d, d),
        (6d, d),
        (7d, d),
        (8d, d),
        (9d, d),
        (d, 𝜀)
    },
    n)
```

<h3>5. Give a programming langauge grammar, using the notation from class, for the programming language described as follows. Programs are made up of a possibly empty sequence of function declarations, followed by a single expression. Each function declaration is of the form f=(p1,…,pm)⇒e where f is the function name (an identifier), each pi is a parameter (also identifiers) and the result (the “body”) is an expression. Expressions can be numeric literals, string literals, identifiers, function calls, or can be made up of other expressions with the usual binary arithmetic operators (plus, minus, times, divide, remainder) and a unary prefix negation and a unary postfix factorial (!). There’s a conditional expression with the syntax x ? y : z. Parentheses are used, as in most other languages, to group subexpressions. Numeric literals are non-empty sequences of decimal digits with an optional fractional part and an optional exponent part. String literals delimited with double quotes with the escape sequences \', \", \n, \\, and \u{hhhhhh} where hhhhhh is a sequence of one-to-six hexadecimal digits. Identifiers are non-empty sequences of letters, decimal digits, underscores, and dollar signs, beginning with a letter or dollar sign. Function calls are formed with an identifier followed by a parenthesized, comma-separated list of expressions.</h3>

<p>The programming language</p>

```
Prog    → Dec* Exp
Dec     → id "=" "(" (id ("," id)*)? ")" "⇒" Exp
Call    → id "(" (Exp ("," Exp)*)? ")"
Exp     → num
        | id
        | string
        | Call
        | "-" Exp
        | Exp ("+" | "-" | "*" | "/" | "%" | "**") Exp
        | Exp "!"
        | Exp "?" Exp ":" Exp
        | "(" Exp ")"
num     → digit+ ("." digit+)? (("E" | "e") ("+" | "-")? digit+)?
id      → letter | "$" (alnum | "_" | "$")*
string  → "\"" char* "\""
char    → "\x00".."\x21"
        | "\x23".."\x5b"
        | "\x5d".."\x10ffff"
        | "\\" ("'" | "\"" | "\\" | "n" | "u{" h h? h? h? h? h? "}")
h     → (digit | hexDigit)
space   → " " | "\t" | "\r" | "\n"
```

<h3>6. For the language in the previous problem, write an abstract syntax specification </h3>

<p>picture here</p>

<h3>7. For the language in the previous problem, give an abstract syntax tree for the program:</h3>

```
gcd = (x, y) => y ? gcd(y, x % y) : x
cube = (x) => x * x * x
"The answer is" + cube(gcd(30, 4!)) + "😦😦"
```

<p>picture here</p>
