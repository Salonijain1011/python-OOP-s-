# python-OOP-s-</br>
# Class and object</br>
 class Car:</br>
   name="mercedes"</br>
   model="S1"</br>
 car1 = Car()</br>
 print(car1.name)</br>

output:- mercedes</br>

# Constructor (init function)</br>
 class Student:</br>
  def __init__(self,name):</br>
    self.name=name</br>
    print("adding new student")</br>
s1 = Student("kirti")</br>
print(s1.name)</br>

output:-adding new student</br>
kirti</br>

# private attribute</br>
 class Account:</br>
   def __init__(self,acc_no,acc_pass):</br>
     self.acc_no = acc_no</br>
     self.__acc_pass = acc_pass</br>
   def reset_pass(self):</br>
     print(self.__acc_pass)</br>

 acc1=Account("1234","asdf")</br>
 print(acc1.acc_no)</br>
 print(acc1.reset_pass())</br>

output:- 1234</br>
asdf</br>
None</br>

# Inheritance</br>
 class Car:</br>
   @staticmethod</br>
   def start():</br>
     print("car started")</br>
   @staticmethod</br>
   def stop():</br>
     print("car stopped")</br>
 class ToyotaCar(Car):</br>
   def __init__(self, name):</br>
     self.name = name</br>
 Car1 = ToyotaCar("fortuner")</br>
 print(Car1.start())</br>

output:- car started</br>
None</br>

# Multiple Inheritance ( one child and two parent)</br>
 class A:</br>
  varA = "welcome to A"</br>
 class B:</br>
  varB = "welcome to B"</br>
 class C(A,B):</br>
  varC = "welcome to C"</br>
 c1 = C()</br>
 print(c1.varA)</br>
 print(c1.varB)</br>

output:- welcome to A</br>
welcome to B</br>

# Super method</br>
 class Car:</br>
  def __init__(self,type):</br>
    self.type = type</br>
  @staticmethod</br>
  def start():</br>
    print("car started")</br>
  @staticmethod</br>
  def stop():</br>
    print("car stopped")</br>
class ToyotaCar(Car):</br>
  def __init__(self,name):</br>
    super().__init__(type)</br>
    self.name = name</br>
    super().start</br>
c1 = ToyotaCar("fortuner")</br>
print(c1.type)</br>

output:- <class 'type'></br>

# Class method</br>
class Person:</br>
  name = "anyone"</br>
  @classmethod</br>
  def ChangeName(cls, name):</br>
   cls.name = name</br>
p1 = Person()</br>
p1.ChangeName("maya")</br>
print(p1.name)</br>
print(Person.name)</br>

output:-maya</br>
maya</br>

# Property method</br>
# Property decorator is used to use the method as a property.</br>
# In this code we are changing the value of attribute using @property method</br>
 class Student:</br>
  def __init__(self,phy,chem,math):</br>
    self.phy=phy</br>
    self.chem=chem</br>
    self.math=math</br>
  @property</br>
  def percentage(self):</br>
    return str((self.phy + self.chem + self.math)/3)</br>
 s1=Student(99,78,56)</br>
 print(s1.percentage)</br>
 s1.phy=45</br>
 print(s1.percentage)</br>

output:- 77.66666666666667</br>
59.666666666666664</br>

# Polymorphism : when a same operator is allowed to have different meaning according to the context</br>
# complex number</br>
class Complex:</br>
  def __init__(self,real,img):</br>
    self.real=real</br>
    self.img=img</br>

  def Shownumber(self):</br>
    print(self.real,"i +",self.img,"j")</br>
num1 = Complex(1,3)</br>
num1.Shownumber()</br>
num2 = Complex(2,4)</br>
num2.Shownumber()</br>

output:- 1 i + 3 j</br>
2 i + 4 j</br>

# add is a dunder function used for addition</br>
class Complex:</br>
  def __init__(self,real,img):</br>
    self.real=real</br>
    self.img=img</br>

  def Shownumber(self):</br>
    print(self.real,"i +",self.img,"j")</br>

  def __add__(self,num2):</br>
    newreal=self.real + num2.real</br>
    newimg=self.img + num2.img</br>
    return Complex(newreal,newimg)</br>
    
num1 = Complex(1,3)</br>
num1.Shownumber()</br>

num2 = Complex(2,4)</br>
num2.Shownumber()</br>

num3=num1+num2</br>
num3.Shownumber()</br>

output:- 1 i + 3 j</br>
2 i + 4 j</br>
3 i + 7 j</br>

# Exercise 1</br>
 class Circle:</br>
  def __init__(self,radius):</br>
    self.radius=radius</br>
  
  def area(self):</br>
    return 3.14 * self.radius ** 2</br>
  
  def perimeter(self):</br>
    return 2 * 3.14 * self.radius</br>

 c1 = Circle(3)</br>

 print(c1.area())</br>

 print(c1.perimeter())</br>

output:-28.26</br>
18.84</br>

# Exercise 2</br>
 class Employee:</br>
  def __init__(self,role,department,salary):</br>
    self.role=role</br>
    self.department=department</br>
    self.salary=salary</br>
  def Showdetails(self):</br>
    print("role =",self.role)</br>
    print("department =",self.department)</br>
    print("salary =",self.salary)</br>

 class Engineer(Employee):</br>
  def __init__(self,name,age):</br>
    self.name=name</br>
    self.age=age</br>
    super().__init__("Engineer","IT","70,000")</br>

 e2= Engineer("saloni","23")</br>
 print(e2.Showdetails())</br>
 # e1 = Employee("Accountant","data",2000)</br>
 # print(e1.Showdetails())</br>

output:-role = Engineer</br>
department = IT</br>
salary = 70,000</br>
None</br>

# Exercise 3 using (__gt__) dunder function (greater than)</br>
 class Order:</br>
  def __init__(self,item,price):</br>
    self.item=item</br>
    self.price=price</br>
  def __gt__(self,ord2):</br>
    return self.price>ord2.price</br>
  
 ord1=Order("chips",100)</br>
 ord2=Order("cake",40)</br>
 print(ord1>ord2)</br>

output:- True</br>

# exception handling</br>
 a = (input("enter value:"))</br>
 print(f"multiplication table of {a} is :")</br>
 try:</br>
  for i in range(1,11):</br>
    print(f"{int(a)} x {i} = {int(a)*i}")</br>
 except:</br>
  print("Invalid input")</br>
 print("end of program")</br>

output:-enter value:hh</br>
multiplication table of hh is :</br>
Invalid input</br>
end of program</br>

   




  

