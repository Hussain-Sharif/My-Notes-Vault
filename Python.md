
> [!NOTE] OOPS
## **Understanding Attributes and Methods:**
```
class Cart:
  flat_discount = 0 # Class Attributes
  min_bill = 100
  def __init__(self):
      self.items = {} # Instance Attributes
  def add_item(self,items,item_name,quantity):
      self.items[item_name] = quantity
  def display_items(self):
      Cart.flat_discount=153 # here value is changed and shown for every instance after this execution. 
      self.flat_discount=143 # This value shown to the Object which runs this method only Other than that other object will still show the class default value or value changed by class
      print(self,type(self),self.items,Cart.flat_discount,self.flat_discount)
a = Cart()
a.display_items()
b=Cart()
Cart.flat_discount=1000
print(a.flat_discount)
print(b.flat_discount)

Here,
Attributes = Properties[class & Instance Attributes]

{outside class}:
Instance Atributes are only Accessed by the `Objects` 
Class Attributes are accessed by both `className` and `Object` 

In General, 
those Attributes are Accessed and Modified outside the Class.

{Inside Class}:
Instance Atributes are only Accessed by the `self` 
Class Attributes are accessed by both `className` and `self` 

{Important Points for Attributes = Properties[class & Instance Attributes]}:
1. ClassName can change the Attribute Value in method. Also, this modified value will be replicated in Other Object instance wherever it trys to access the class Attribute.
2. Here Object specific Class Attribute have and can make changes.


Methods:
- Instance Methods
- Class Methods
- Static Methods

Instance Attribute Modifications made in Instance Methods CALLED by Object
[@classmethod above the method]Class Attribute Modifications made in Class Methods CALLED by ClassName
[@staticmethod above the method] Static Methods are used as utility Methods CALLED by ClassName



```

>End


### **Encapsulation** 
Bundling Objects & Methods into a Single Entity{Class}
such process is called Encapsulation
- Data Protection
- Access Restriction

## **Access Modifiers**
1. By Default, All the methods and Attributes are Public
2. for make the Attribute Private we need to use __ as prefix to the attribute in which the Object can't access it to make it Access and modify use get_Attributename {which is a getter returns something} set_Attributename {which sets the Attributename this should not reutrn anything}.
3. The prefix of `get` and `set` is followed by `__attributename` for the methods 

## **Sub-classes, Inheritance, Composition, Inheritance Chaining and MRO** 

```
class Product:
   def __init__(self, name, price, deal_price, ratings):
       self.name = name
       self.price = price
       self.deal_price = deal_price
       self.ratings = ratings
       self.you_save = price - deal_price
   def display_product_details(self):
       print("Product: {}".format(self.name))
       print("Price: {}".format(self.price))
       print("Deal Price: {}".format(self.deal_price))
       print("You Saved: {}".format(self.you_save))
       print("Ratings: {}".format(self.ratings))

class ElectronicItem(Product):
   def set_warranty(self, warranty_in_months):
       self.warranty_in_months = warranty_in_months
      
   def get_warranty(self):
       return self.warranty_in_months

p = Product("TV",45000, 40000, 3.5)
p.set_warranty(24)


Here, 
In Sub-Class we can create new Attribute and set~Get values using Object only........
- Superclass cannot access the methods and attributes of the subclass.
- We can call methods defined in superclass from the methods in the subclass.

Inheritance and Composition:

Inheritance:
is-a Relationship, accessing the parent class properties and methods from child class

Composition:
has-a Relationship, Combining the different instance of classes into single class which doesn't relate to eachother and bringing them into single class and creating Instances inside that single Class of those individual classes. {Combining the instances of Different Class entities and using them inside a Master Single Class}.
--->Below is the ExAMPLE:

class Battery:
    def __init__(self, capacity):
        self.capacity = capacity
        self.charge = capacity
    
    def use_power(self, amount):
        self.charge = max(0, self.charge - amount)
        return f"Used {amount}% power. Remaining: {self.charge}%"

class Screen:
    def __init__(self, size):
        self.size = size
    
    def display(self, content):
        return f"Displaying '{content}' on {self.size} screen"

class Camera:
    def __init__(self, megapixels):
        self.megapixels = megapixels
    
    def take_photo(self):
        return f"Took photo with {self.megapixels}MP camera"

class Smartphone:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model
        self.battery = Battery(100)      # Has-a relationship
        self.screen = Screen("6.1 inch") # Has-a relationship
        self.camera = Camera(12)         # Has-a relationship
    
    def make_call(self):
        battery_status = self.battery.use_power(5)
        return f"Making call on {self.brand} {self.model}. {battery_status}"
    
    def take_selfie(self):
        photo = self.camera.take_photo()
        display = self.screen.display("Selfie")
        battery_status = self.battery.use_power(3)
        return f"{photo}. {display}. {battery_status}"

# Usage
phone = Smartphone("iPhone", "13")
print(phone.make_call())
print(phone.take_selfie())
```
### When to Use Which?
### Use Inheritance When:
- You have a clear "is-a" relationship {Car is a Vehicle}
    
- You want to extend existing functionality
    
- Classes share common behavior and attributes
    
- You need polymorphism
    
**Example**: `Dog` is an `Animal`, `Student` is a `Person`

### Use Composition When:
- You have a "has-a" relationship {Car has a Tyre}
    
- You want to combine different functionalities
    
- You need more flexibility
    
- You want to avoid deep inheritance hierarchies
    
**Example**: `Car` has an `Engine`, `Student` has `Courses`

### Combination of Both:
```
# Base classes for inheritance
class Vehicle:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
    
    def start(self):
        return f"{self.make} {self.model} is starting"
    
    def stop(self):
        return f"{self.make} {self.model} has stopped"

# Components for composition
class GPS:
    def __init__(self):
        self.current_location = "Unknown"
    
    def navigate_to(self, destination):
        return f"Navigating to {destination}"

class Entertainment:
    def __init__(self):
        self.current_song = None
    
    def play_music(self, song):
        self.current_song = song
        return f"Now playing: {song}"

# Using both inheritance and composition
class SmartCar(Vehicle):  # Inheritance: SmartCar IS-A Vehicle
    def __init__(self, make, model, year):
        super().__init__(make, model, year)
        self.gps = GPS()              # Composition: SmartCar HAS-A GPS
        self.entertainment = Entertainment()  # Composition: SmartCar HAS-A Entertainment
        self.autopilot = False
    
    def enable_autopilot(self):
        self.autopilot = True
        return "Autopilot enabled"
    
    def smart_navigation(self, destination):
        return self.gps.navigate_to(destination)
    
    def play_favorite_music(self):
        return self.entertainment.play_music("Your favorite playlist")

# Usage
my_tesla = SmartCar("Tesla", "Model 3", 2023)
print(my_tesla.start())              # Inherited method
print(my_tesla.enable_autopilot())   # SmartCar specific method
print(my_tesla.smart_navigation("Home"))  # Using composed GPS
print(my_tesla.play_favorite_music())     # Using composed Entertainment

```


#### Method Override:
-->A Subclass have a same named method in which same named method is also present in Parent Class after inheritance that method get's override completely 

--> In Inheritance all the properties and methods are called everywhere Like we do with single class instance...

#### To Extend the Method:
--> We use super() in the respective method not to override but extend that Method Functionality only 
==>It can be __ init __ method or any other method that we want to extend the Functionality of the SUper Class from the Sub-class

###  Method Resolution Order (MRO) in Python

***MRO answers a simple question: when accessing an attribute or method on an object, in what order does Python search the class hierarchy to find it?***

Why we need to know :
- To avoid ambiguity/Misconception of the Order of which accessing the attribute and method on an Object 
- To maintain consistent Order with the declared parent order (left-to-right). of which accessing needs be done for multiple instance levels
- Understanding overrides
##### **The method resolution order (MRO) is the sequence Python follows to look up attributes and methods for a class.**

-->with Method Overriding: 

```
class A: 
    def speak(self): return "A"

class B(A): 
    pass

class C(A): 
    def speak(self): return "C"

class D(B, C):
    pass

print(D.mro()) 
print(D.mro) #  a tuple with the same information.
# [<class '__main__.D'>, <class '__main__.B'>, <class '__main__.C'>, <class '__main__.A'>, <class 'object'>]

print(D().speak())  # "C" (found in C before A)

```

--> with Method Extending:
```
class A: 
    def f(self): return "A"
class B(A): 
    def f(self): return "B->" + super().f()
class C(A): 
    def f(self): return "C->" + super().f()
class D(B, C): 
    pass

print(D.mro())       # [D, B, C, A, object]
print(D().f())       # "B->C->A"

```

“The MRO is the precise, linear order Python uses to search for attributes across a class hierarchy—computed by C3 linearization—ensuring left-to-right parent precedence, no duplicates, and consistent cooperation via super().”


## **Abstraction**

-- The Process of **hiding Complexity** and Showing **Essential Info** in simple way.
- **Abstract Classes** act as a template for other classes
- Defines methods that **must be implemented** by subclasses.
- Similar to regular classes, abstract classes can have **constructors, attributes and methods.**

===> "**We cannot create objects of an abstract class as they are only meant to be inherited.**"


Abstract classes are created using the **abc (Abstract Base Class)** module.
```
from abc import ABC
```

--**ABSTRACT Methods** are created inside the **Abstract class** but Implemented inside the sub-classes which are Inherited them.

To create **ABSTRACT Methods**. we need to IMPORT 
```
from abc import ABC
from abc import abstractmethod # <<--------Here we importing them
class Vehicle(ABC):
  @abstractmethod
  def start(self):
    pass
        
  @abstractmethod
  def stop(self):
    pass
```

- **Subclasses inheriting** from an abstract class must implement all of its **abstract methods**.

====> " **An abstract class can have regular methods along with abstract methods. A regular method defined in an abstract class can be used by all sub classes.**"
- Where in the Regular Classes also we can Implement the LOGIC Directly inside the Abstract Class.
## **Polymorphism:**
The ability of **Functions**, **Operators**, or **Objects** to change their **Behavior** based on the situation.

### Operator Polymorphism:
 `+` is One such Operator Example for Polymorphism 
 
This is Also a ***Operator OverLoading*** \[using the **same operator** or **function name** to perform **different operations** based on data types or arguments.] 

### Function Polymorphism:
Same thing here also same function name with different datatype of Arguments/Parameters
Example: len("abc") ~ len(\[1,2,3])~len((1,2,3))~len(dict())

### Class Polymorphism:
Python Allows multiple classes to have same named method. \[That ***shows method/function to execute in different situation*** like in this case different instance of different objects]

Slowly!

Understand, **Method Overriding and Method Overloading**

#### Method Overriding:
The ability of Subclass to Override the method of same in super class.
{Remember: From abstract Class we just Implement the methods NO Overriding Concept there}

#### Method Overloading:
In a class we are having multiple methods of same name with different Number of Attributes.

Done!! OOPS Done!.
