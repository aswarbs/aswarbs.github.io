---
layout: page
title: Mudskip
---

For our fourth year Dissertation, Toby and I made [Mudskip](https://github.com/tambercore/hottnat), a symbolic theorem prover designed to reason with Natural Langauge statements through the derivation of dependent types, expressed in [Agda](https://agda.readthedocs.io/en/latest/getting-started/what-is-agda.html). For example, `Amber likes gouda and brie` becomes:

```haskell
postulate
  Entity : Set
  likes : Entity → Entity → Set
  isAmber : Entity → Set
  isGouda : Entity → Set
  isBrie : Entity → Set


record Amberᵣ : Set where
  constructor Amber꜀
  field
    e₁ : Entity
    p : isAmber e₁


record Goudaᵣ : Set where
  constructor Gouda꜀
  field
    e₁ : Entity
    p : isGouda e₁


record LikesAmberGoudaᵣ : Set where
  constructor LikesAmberGouda꜀
  field
    e₁ : Amberᵣ
    e₂ : Goudaᵣ
    p : likes (Amberᵣ.e₁ e₁) (Goudaᵣ.e₁ e₂)


record Brieᵣ : Set where
  constructor Brie꜀
  field
    e₁ : Entity
    p : isBrie e₁


record LikesAmberBrieᵣ : Set where
  constructor LikesAmberBrie꜀
  field
    e₁ : Amberᵣ
    e₂ : Brieᵣ
    p : likes (Amberᵣ.e₁ e₁) (Brieᵣ.e₁ e₂)


record LikesAmberGouda×LikesAmberBrieᵣ : Set where
  constructor LikesAmberGouda×LikesAmberBrie꜀
  field
    e₁ : LikesAmberGoudaᵣ
    e₂ : LikesAmberBrieᵣ



```