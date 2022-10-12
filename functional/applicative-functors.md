# Applicative Functors
A [[functors]] cannot map a function that is inside a Functor, for example `Just (3 *)`, over another Functor, for example `Just 5`, with the method `fmap`. 
Applicative Functors is a functors that map a function inside a Functor over another Functor. It defines two methods: `pure` and `<*>`. The class definition:

```haskell
class (Functor f) => Applicative f where
    pure :: a -> f a
	<*> :: f (a -> b) -> f a -> f b
```

`pure`: `f` plays the role of the applicative functor instance. It takes one value and returns an Applicative Functor with that value inside, like a box analogy where we put a value inside a box(Applicative Functor);

`<*>`:  `f` plays the role of the applicative functor instance. It takes a functor that has a function in it and another functor and extract that function from the first functor and then maps it over the seconde functor. 

Exampe of the `Applicative` instance implementation for `Maybe`:

```haskell
instance Applicative Maybe where
  pure = Just
  Nothing <*> _ = Nothing
  (Just f) <*> something = fmap f something
```


With [[functors]], you can just map a function over a functor and then you can't get the result out in any general way, even if the result is a partially applied function. Applicative functors, on the other hand, allow you to operate on several [[functors]] with a single function. Example:

```haskell
pure (+) <*> Just 3 <*> Just 5
```
