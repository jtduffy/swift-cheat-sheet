# Swift 4 Cheat Sheet

[![N|Solid](https://devimages-cdn.apple.com/assets/elements/icons/swift/swift-64x64.png)](https://nodesource.com/products/nsolid)

[Official Site](https://developer.apple.com/swift/)

[Apple's Language Reference](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/TheBasics.html#//apple_ref/doc/uid/TP40014097-CH5-ID309)  *<-- This is very, very good*

##### Type, Variables and Constants
###### Basic Types
- Character
- String
- Int
- Double
- Float
- Bool
###### Define a constant:
```swift
let age: Int = 30
let pi: Double = 3.14159
let message:String = "Hello world"
let dollarSign:Character = "$"
```
###### Define a variable:
```swift
var currentTemp: Double = 98.6
var linesOfCode: Int = 100
var x:Double = 0.0, y:Double = 0.0, z:Double = 0.0
var isCompleted: Bool = false
```
Types in Swift can be inferred.  Note that there is no character literal in Swift.  If a character is desired, it must be typed explicitly.
```swift
let age = 30
let pi = 3.14159
let message = "Hello world"
```
###### Type Conversion
Numeric type conversion in Swift must be explicit.
```swift
var currentTempAsDouble = 98.6
var currentTempAsInt = Int(currentTempAsDouble)
var hoursWorked = 40
var hourlyRate = 15.33
var totalPaycheck = Double(hoursWorked) * hourlyRate
```
###### Strings
String concatenation
```swift
let hello = "Hello"
var greeting = hello + " world!"
greeting += "  Hello again"
```
Multi-line
```swift
let myBigString = """
Swift allows Strings to
contain multiple lines
by enclosing the String 
in triple quotation marks
"""
```
###### Tuples
Tuples are data that is represented by more than a single type.
```swift
let mapCoords: (Double, Double) = (2.3, 5.9)    //Explicit types
let operationStatus = ("Failure", -1)           //Inferred types
let statusString = operationStatus.0            //Grab 1st value from tuple
let statusCode = operationStatus.1              //Grab 2nd value from tuple

let dailyAvgTemp = (day: "Monday", temp: 77.3)	//Named members in the tuple
let dayOfWeek = dailyAvgTemp.day
```
##### Collection Types
Built in Swift collection types include arrays, sets and dictionaries.

- Collection types are mutable if assigned to a variable `(var)` and immutable if assigned to a constant `(let)`
- Collection types are implemeted as generics
- A collection must be explicit about the types of keys/values it stores (no mixing different types in an array, for example)

###### Arrays
```swift
var intArray = [Int]()		//Explicit initialization with type

//Array literal initialization with String type
var vehicles = ["car", "truck", "airplane", "motorcycle"]

var anotherArray = []		//Empty untyped array
anotherArray.append(44)		//anotherArray now is an [Int] array

//Init an array of Strings with the default value of "hello" and a size of 10
var a = Array(repeating: "hello", count: 10)

a.count						//Get the number of elements in the Array
a.isEmpty					//Am I empty?
a.append("goodbye")			//Add a value to the end of an array
a += ["cya later"]			//Another way to append
a[0] = ""					//Modify element at index 0
a.insert("hello???", at: 5)	//Insert a new element at index 5
a.remove(at: 5)				//Remove the element as index 5
a.removeLast()				//Remove final array element
```

###### Sets
```swift
var mySet = Set<Int>()		//Empty Set using initializer syntax
var primes: Set = [2, 3, 5]	//Init a set with an Array literal

mySet.isEmpty()				//Am I empty?
mySet.insert("foo")			//Insert a new element
mySet.remove("foo")			//Remove from set, returns nil if the element doesn't exist
mySet.contains("bar")		//Does the set contain that element?
```
See the language reference for Set operation details (intersect, union, etc).

###### Dictionary
```swift
var d = [String: Int]()				//Init a String -> Init dictionary
var instances = ["s1": 2, "s2": 4]	//Init with a dictionary literal

instances.isEmpty()					//Am I empty?
instances["s3"] = 4					//Add new element
instances["s2"] = 0					//Update existing element
instances["s3"] = nil				//Remove element
```
##### Functions/Methods
```swift
//Assume Person and Response classes exist
func sayHello(to person:Person) {
	let fullGreeting = "Hello there \(person.name)!"
    print(fullGreeting)
}

//Prints "Hello there mom!"
let mom:Person = Person("mom")
sayHello(to: person)

//Return a value
func multiple(_ a:Int, by b:Int) -> Int {
	return a * b
}
```
