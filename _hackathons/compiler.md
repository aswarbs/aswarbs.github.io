---
layout: page
title: Divine Intellect Compiler
---

Toby and I made a "Divine Intellect Compiler" at [Hack Sheffield 2024](https://devpost.com/software/divine-intellect-compiler) which <span style="color:rgb(237, 204, 17);">**won best prize!**</span>. We made a working programming language with a custom compiler, and an IDE to code in. The most distinctive feature of the language is its use of refinement types:

```python
type bankbalance(a : i32) where {
    a >= 0,
};

fn add_to_balance(bal: bankbalance, amount: bankbalance) -> bankbalance {
    return(bal + amount)
};

fn double_balance(bal: bankbalance) -> bankbalance {
    return(?)
};

fn main() -> i32 {
    a: bankbalance;
    a := 100 - 50;
    a := double_balance(double_balance(a));
}

```

`bankbalance` is a refinement type, an integer which must be greater than or equal to 0. If the program includes a negative `bankbalance` variable, the typechecker will fail and return a full stacktrace explaining why it failed. Agda-like [holes](https://agda.readthedocs.io/en/v2.6.0.1/language/lexical-structure.html) are supported in the language - in `double_balance`, the compiler will attempt to fill in the hole (?) by using the context of the surrounding program. It will only return valid programs which pass the typechecking process.
