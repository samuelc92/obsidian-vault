Linearizable Systems essentially means "behave as there is only a single copy of the data, and all operations on it are atomic". 

In a linearizable system, we have a total order of operations if the system behaves as if there is only a single copy of the data, and every operation is atomic, this means that for any two operations we can always say which one happened first.