# Monoids
A monoid is when you have an [[associativity]] function and a value which acts as an identity with respect to that function. When something acts as identity with respect to a function, it means that when called with that function and some other value, the result is always equal to that other value. `1` is the identiy with respect to `*` function and, `[]` is the identity with respect to `++` function. Monoid type class defined:

```haskell
class Monoid m where
  mempty :: m -- represents the identity value for a particular Monoid
  mappend :: m -> m -> m -- it is the associativity function
  mconcat :: [m] -> m
  mconcat = foldr mappend mempty
```

##  Properties
 - The function takes two parameters;
 - The parameter and the returned value have the same type;
 - [[associativity]] function;

## Laws
- `mempty 'mappend' x = x` (mempty act as the identity with respect to mappen)
- `x mappend 'mempty' = x`
- `(x 'mappend' y) 'mappend' z = x 'mappend' (y 'mappend' z)` (mappend has to be [[associativity]])

## Examples
Lists are monoids

```haskell
instance Monoid [a] where -- monoids requires a concrete type it is the reason we wrote Monoid [a] instead of Monoid []
  mempty = []
  mappend = (++)
```

Maybe

```haskell
instance Monoid a => Monoid (Maybe a) where -- `Maybe a` is a Monoid only if `a` is also and instance of the Monoid
  mempty = Nothing
  Nothing `mappend` m = m
  m `mappend` Nothing = m
  Just m1 `mappend` Just m2 = Just (m1 `mappend` m2)
```
	