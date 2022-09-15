QuickSort is a Divide and Conquer algorithm, it picks an element as a pivot and partitions the given array around the picked pivot. Some ways to pick a pivot:

- Always pick the first element as a pivot
- Always pick the last element as a pivot (showed in the image below)
-  Pick a random element as a pivot
- Pick median as the pivot

![[quick-sort.jpg]]

The key process in quickSort is a partition. The target of partitions is, given an array and an element x of an array as the pivot, put x at its correct position in a sorted array and put all smaller elements(small than x) before x, and put all greater elements (greater than x) after x. All this should be done in linear time. Then call recursively the quickSort method for the smaller elements, add the pivot and. call recursively the quickSort method for the bigger elements.

```haskell
quicksort :: (Ord a) => [a] -> [a]
quicksort [] = []
quicksort (x:xs) =
    let smallerSorted = quicksort[a | a <- xs, a <= x]
	    biggerSorted = quicksort [a | a <- xs, a > x]
	in smallerSorted ++ [x] ++ biggerSorted
```
