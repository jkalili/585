# Homework 2

### Adrian Leung, Nick Morgan, Jason Kalili

<br>

## Problem Set

![Wren Rules](./assets/hw3/wren_ast_rules.png)

<h3>1. Problem 1.4.3 in Slonneger and Kurtz -

Draw an abstract syntax tree for the following Wren program:</h3>

```
program binary is
  var n,p : integer ;
begin
  read n; p := 2;
  while p<=n do p := 2*p end while ;
  p := p/2;
  while p>0 do
    if n>= p then write 1; n := n–p else write 0 end if;
    p := p/2
  end while
end
```

<h3>2. Problem 5.1.1 in Slonneger and Kurtz -

Correctly parenthesize each of these lambda expressions:

<ol style = 'list-style-type: lower-latin;'>
    <li> λx . x λy . y x <br><u>ans</u>
    <li> (λx . x) (λy . y) λx . x (λy . y) z <br><u>ans</u>
    <li> (λf . λy . λz . f z y z) p x <br><u>ans</u>
    <li> λx . x λy . y λz . z λw . w z y x <br><u>ans</u>
</ol>
</h3>

<h3>3. Problem 5.1.2 in Slonneger and Kurtz</h3>

<h3>4. Problem 5.1.3 in Slonneger and Kurtz</h3>

<h3>5. Problem 5.2.3 in Slonneger and Kurtz</h3>

<h3>6. Problem 5.2.7 (a) in Slonneger and Kurtz</h3>

<h3>7. Problem 8.5.1 in Slonneger and Kurtz</h3>

<h3>8. Problem 8.5.9 in Slonneger and Kurtz</h3>

<h3>9. Problem 8.6.3 in Slonneger and Kurtz</h3>

<h3>10. Problem 8.6.6 in Slonneger and Kurtz</h3>
```
