# General syntax
## Multi-line function
```scala
def add(a:Int, b:Int):Int = {
    return a + b
}
```
## Single-line function
```scala
val add = (a:Int, b:Int) => a + b
```

# Higher-order functions
## .map(fn)
```scala
val array = Array(1,2,3,4,5,6)
val arrayDoubled = array.map(n => n * 2);
// arrayDoubled = [2, 4, 6, 8, 10, 12]
```

## .filter(fn)
```scala
val array = Array(1,2,3,4,5,6)
val greaterThanFour = array.filter(n => n > 4)
// arrayDoubled = [5, 6]
```

## .reduce(fn)
Reduce uses the first element of the array. Reduce functions may be parallellized.
```scala
val array = Array(1,2,3,4,5,6)
val sumOfArray = array.reduce(total, n => total + n);
// sumOfArray = 21
// Step 1: total = 1,   n = 2
// Step 2: total = 3,   n = 3
// Step 3: total = 6,   n = 4
// Step 4: total = 10,  n = 5
// Step 5: total = 15,  n = 6
```

## .reduceByKey(fn)
Groups collection by tuple key. You implement the aggregate function (fn). Can only be performed on RDD collections.
### Some aggregate function examples
```scala
def sum = (current:Int, n:Int) : Int {
    return current + n;
}
def max = (current:Int, n:Int) : Int {
    return Math.max(current, n)
}
```
### Example
```scala
val array = sc.parallelize(Array(
(45, 10), 
(45, 5), 
(50, 5), 
(30, 10), 
(30, 15) 
))
val aggregate = array.reduceByKey((current, n) => current + n);
// aggregate = [ (50, 5), (45, 15), (30,25) ]
```

## Average value of tuples
```scala
val array = sc.parallelize(Array(
(45, 10), 
(45, 5), 
(50, 5), 
(30, 10), 
(30, 15) 
))

val averageTuples = array.mapValues(x => (x, 1)).reduceByKey((x, y) => (x._1 + y._1, x._2 + y._2)).mapValues(y => 1.0 * y._1 / y._2)
averageTuples.foreach(println)
```
![alt text](https://i.stack.imgur.com/vAWTK.jpg)

Source: http://stackoverflow.com/a/40101724