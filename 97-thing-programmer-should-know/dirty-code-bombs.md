We have many ways of measuring and controlling the degree of coupling and complexity of our code. The values of these counts do correlate with code quality. Two of a number of metrics that measure coupling are fan-in and fan-out. 

Consider fan-out for classes: It is defined as the number of classes referenced either directly or indirectly from a class of interest. You can think of this as a count of all the classes that must be compiled before your class can be compiled.

Fan-in, on the other hand, is a count of all classes that depend upon the class of interest. Therefore we can calculate an instability factor using / = fo/(fi +fo). As / approaches 0, the package becomes more stable. As / approches 1, the package becomes unstable. 
