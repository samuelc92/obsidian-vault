A function is considered associative when the order of the parameters does not matter, the result will always be the same. Consider the function `*` , it doesn't matter if we do `1 * x` or `x * 1` the result is always `x`. Similarly, `++` both `[1,2,3] ++ []` and `[] ++ [1,2,3]` have the same result.

If a function has three or more values and it does not matter the order of when the values because the result is the same, it is also called a associative function. For example:

```haskell
(3 * 2) * (8 * 5) == 3 * (2 * (8 * 5))

"la" ++ ("di" ++ "da") == ("la" ++ "di") ++ "da"

(5 - 3) - 4 <> 5 - (3 - 4)  -- not an associative function
```