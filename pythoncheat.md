# Python 3.6+ Cheat Sheet
### Not for beginners

## Data Types
### Strings
```
x = "Hello"
x = 'Hello'   # python only
```

### Int
```
x = 3
```

### Float
```
x = 3.3333333   #7 decimal places percision
```

### Double
```
x = 3.333333333333333   #15 decimal places percision 
```

Turn int,float,double to string
```
x = 3
print(str(x))    #prints 3 as a string
```

## Lists
Create a list
```
myList = [1,2,3]
```

Get value from position (starting from 0) in list (indicies)
```
myList[2]     #prints 3
```

## Dictionary
Create a dictionary
```
myDict = {'A':4, 'B':5, 'C':9}
```

Reference by key
```
myDict['C']     #prints 9
```

Overwrite value of key in dictionary
```
myDict['B'] = 14
```

## Tuple
Tuple allows you to collect different data types
Cant reassign values in a tuple
Create a tuple
```
myTup = (54, 'Hello', [1,2,3,4])
```

Get value from tuple
```
myTup[2]      #prints [1,2,3,4]
```

Get value from list stored in tuple
```
myTup[2][0]
```

## Get the type of something
```
type(myList)
```
```
type(myTup[1])
```

## Python help (command line)
```
help(myList)
```

## Append to list
Adds paramater to list
```
myList.append(14)
```

## Functions
```
def myFunc():
    # code goes here
```

```
def retInt(x):
    return x
```

## Invoke vs Import
Check if invoked from command line or imported from another file
```
if __name__ == '__main__':
    print("invoked")
else:
    print("imported")
```

## Classes
Classes are a way to collect both fuctions and data which can have different
instances of the same class with different data inside of them
```
class myClass:
    oneval = 17
    
C = myClass()
print(C.oneval) #prints 17
```

Member function
```
class myClass:
    oneval = 17
    def div(self, var):   #self is first argument
        return var/self.oneval    #returns var divided by 17

C = myClass()
#invoke function dif from myClass
print(myClass.div(3))     #prints 3/17 as integer
```

Change the value of a member variable in the above examples
```
C.oneval = 4
```

Two instances of a class
Does the same function but references different data
```
C = myClass()
B = myClass()
```

## Built in Class Functions
__init__ is the constructor for the class
set up to take only one argument
```
class myClass:
    def __init__ (self, inval):
        self.oneval = inval

C = myClass(4)   #replaces the need of C.oneval = 4
```

__repr__ is the thing that gets invoked when you print class
```
class myClass:
    hellostr = "Hello"
    def __repr__(self):
        return hellostr

C = myClass
print(myClass)    #prints "Hello"
```

## Inherit a class
A specific class with all the same functionality but with additional things
```
class myClass:
    def func1():
        # do things

# inherit class myClass, so that newClass has func1 from myClass
class newClass (myClass):
    name2 = 'Ronin'
```

## Catching errors
Using try loops:
```
class myClass:
    def func(self, int_arg):
        try:
            return int_arg/3
        except:
            print("Must pass integer")
            return 0

B = myClass
print(B.func(3))      #returns 1
print(B.func('hi'))   #returns 0 because of type error
```

Try loop for specific error
```
class myClass:
    def func(self, int_arg):
        try:
            return int_arg/3
        except TypeError:         #Error with datatype
            print("Must pass integer")
            return 0
        except:         #any other error
            print("General Error")
            return 0

B = myClass
print(B.func(3))      #returns 1
print(B.func('hi'))   #returns 0 because of type error
```

