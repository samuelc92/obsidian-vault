Functors are things that can be mapped over things, like `Lists`, `Maybe`, `trees`, and such. So a Functor maps over a thing applying a function(transformation) on it. When we call `fmap (+3) [1,2,3] (List-Functor)`, the function(transformation) `(+3)` is applied in each element of the list. Another example is mapping over functions, when we call `fmap (+3) (*3)`, the function(transformation) `(+3)` is applied in to the eventual output of `(*3)`, which is just a composition `fmap (+3) (*3)` is equal `(+3) . (*3)`. The result is still a function, only when we give a number, it will be applied to the functions.


Functors should satisfy some laws.

## Functor Laws
 - If we map the `id` (identity function) function over a functor, the functor that we get back should be the same as the original functor. That means if we map `id` function over a Functor, it should be the same as just calling `id` with the same functor.
 - Composing two functions and then mapping the resulting function over a functor should be the same as first mapping one function over the functor and then mapping the other one. That means that `fmap (f . g) = fmap f . fmap g`. Or to write it in another way, for any functor *F*, the following should hold: `fmap (f . g) F = fmap f (fmap g F)`.

If a type obeys both laws, we can make assumptions about how it will act. If a type obeys the functor laws, we know that calling `fmap` on a value of that type will only map the function over it nothing more. This leads to code that is more abstract and extensible, because we can use laws to reason about behaviors that any functor have and make functions that operate reliably on any functor. 

## Breaking the Functor Law

Example of a type that is an instance of Functor but cann't be considered as a Functor because it breaks the first law.

```haskell
data CMaybe a = CNothing | CJust Int a deriving(Show)
instance Functor CMaybe where
  fmap f CNothing = CNothing
  fmap f (CJust counter x) = CJust (counter + 1) (f x)
```

Mapping the `id` function over the CMaybe returns a differente value from just calling `id`  over CMaybe. 

Ex: `fmap id (CJust 0 "haha") != id (CJust 0 "haha")`. 

Even though CMaybe is an instance of Functor typeclass, it doesn't obey the Functor laws and is therefore not a functor.


