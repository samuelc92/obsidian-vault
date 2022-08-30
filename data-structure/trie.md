# Trie

It is a data structure that stores a set of strings as a sorted tree. Each node has the same number of pointers as the number of alphabet characters. It can look up a word in the dictionary by using its prefix. 
Trie is also referred to as the digital tree or the prefix tree. Trie allows us to insert and find strings in O(L) time, where L is the length of a single word.
Another benefit of Trie is that we can easily print all words in alphabetical order, which is not easy with hashing. 

![[trie.jpg]]

The main disadvantages of tries is that they require a large amount of memory to store strings. There are many node pointers for each node.

## Use cases

- Auto-Complete and Search for Search Engines
- Genome Analysis
- Data Analytics
- Browser History
- Spell Checker