## Homework 5


1. Give a Denotational Semantics for Bella.

```
ℰ⟦n⟧m = n
ℰ⟦i⟧m = if m(i)=(NUM,x,_) then x else ⊥
ℰ⟦true⟧m = 1
ℰ⟦false⟧m = 0
ℰ⟦-e⟧m = -ℰ⟦e⟧m
ℰ⟦!e⟧m = if ℰ⟦e⟧m = 0 then 1 else 0
ℰ⟦e₁ + e₂⟧m = ℰ⟦e₁⟧m + ℰ⟦e₂⟧m
ℰ⟦e₁ - e₂⟧m = ℰ⟦e₁⟧m - ℰ⟦e₂⟧m
ℰ⟦e₁ * e₂⟧m = ℰ⟦e₁⟧m * ℰ⟦e₂⟧m
ℰ⟦e₁ / e₂⟧m = ℰ⟦e₁⟧m / ℰ⟦e₂⟧m
ℰ⟦e₁ % e₂⟧m = ℰ⟦e₁⟧m rem ℰ⟦e₂⟧m
ℰ⟦e₁ < e₂⟧m = if ℰ⟦e₁⟧m < ℰ⟦e₂⟧m then 1 else 0
ℰ⟦e₁ <= e₂⟧m = if ℰ⟦e₁⟧m > ℰ⟦e₂⟧m then 0 else 1
ℰ⟦e₁ == e₂⟧m = if ℰ⟦e₁⟧m = ℰ⟦e₂⟧m then 1 else 0
ℰ⟦e₁ > e₂⟧m = if ℰ⟦e₁⟧m > ℰ⟦e₂⟧m then 1 else 0
ℰ⟦e₁ >= e₂⟧m = if ℰ⟦e₁⟧m < ℰ⟦e₂⟧m then 0 else 1
ℰ⟦e₁ != e₂⟧m = if ℰ⟦e₁⟧m = ℰ⟦e₂⟧m then 0 else 1
ℰ⟦e₁ && e₂⟧m = if ℰ⟦e₁⟧m=0 ∨ ℰ⟦e₂⟧m=0 then 0 else 1
ℰ⟦e₁ || e₂⟧m = if ℰ⟦e₁⟧m=1 ∨ ℰ⟦e₂⟧m=1 then 1 else 0
ℰ⟦e₁ ** e₂⟧m = let x=ℰ⟦e₁⟧m and y=ℰ⟦e₂⟧m in
                if x=0 ∧ y=0 then ⊥ else xʸ

//TERNARY
ℰ⟦e₁ ? e₂ :e₃⟧m = if ℰ⟦e₁⟧m ≠ 0 then ℰ⟦e₂⟧m else ℰ⟦e₃⟧m

ℰ⟦ie₁ ... eₙ⟧m = if m(i)=(FUN,f,n) then f(ℰ⟦e₁⟧m, ... ℰ⟦eₙ⟧m) else ⊥

Ꮥ⟦let i = e⟧(m,o)= if  m(i) ≠ UNDEF then ⊥ else (m[ℰ⟦e⟧m/i],o)

Ꮥ⟦print e⟧(m,o) = (m,o•ℰ⟦e⟧m)

Ꮥ⟦i=e⟧(m,o)= if m(i)= (NUM,-,RW) then (m[ℰ⟦e⟧m/i],o) else ⊥

Ꮥ⟦while e b⟧(m,o) = W(m,o) where W=(
    if ℰ⟦e⟧m=0 then (m,o) else W(ℬ⟦b⟧(m,0))
)

Ꮥ⟦fun i p₁...pₙ⟧(m,o)=if m(i) ≠ UNDEF then ⊥ else (m[("FUN",[p₁...pₙ],e,n)/i],o)

ℬ⟦block s₁ ... pₙ⟧(m,o) = Ꮥ⟦sₙ⟧()

℘⟦program b⟧ = ℬ⟦b⟧(mₒ, []) ↓ 1
               let(m,o)=ℬ⟦b⟧(m, o) in o
```

ℰ ℘ ℬ Ꮥ 

