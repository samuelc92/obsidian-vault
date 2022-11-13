# Monads

Monads takes the [[applicative-functors]] knowledge and upgrade it thus every Monad is an [[applicative-functors]]. Monads takes a fancy value (e.g: Maybe, list, Either, etc.), get the value inside the context, apply this value to a function, which takes a normal value and return a fancy one, then return the result of the function. The class definition:

```haskell
class Monad m where
  return :: a -> m a
  
  (>>=) :: m a -> (a -> m b) -> m b
  x >> y = x >>= \_ -> y

 fail :: String -> m a 
 fail msg = error msg
```

The function `>>=` takes a value with a context (a monadic value) and feeding it to a function that takes a normal value and returns one that has context. 

Example of a Maybe Monads:

```haskell
instance Monad Maybe where
  return x      = Just x
  Nothing >>= f = Nothing
  Just x >>= f  = f x
  fail _        = Nothing
```

## Laws

- Left Identity:  `return x >>= f == f x`
- Right Identity: `x >>== return == x`
- [[associativity]]: `(m >>= f) >>= g == m >>= (\x -> f x >>= g)`