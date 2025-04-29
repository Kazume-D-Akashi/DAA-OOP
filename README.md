# DAA-OOP
(OPP)
Aim: Develop programs to demonstrate function overloading and overriding within 
classes.
Code:
#include <iostream> // Step 1: Include standard library
using namespace std;
class FunctionOverloading { // Step 2: Define a class for Overloading
public:
 // Step 3: Function Overloading - same function name but different parameters
 void display(int num) {
 cout << "Integer: " << num << endl;
 }
 void display(double num) {
 cout << "Double: " << num << endl;
 }
 void display(string text) {
 cout << "String: " << text << endl;
 }
};
class Base { // Step 4: Define Base Class for Overriding
public:
 virtual void show() { // Step 5: Virtual function to be overridden
cout << "Base Class Show Function" << endl;
 }
};
class Derived : public Base { // Step 6: Derived Class
public:
 void show() override { // Step 7: Overriding the show() function
 cout << "Derived Class Show Function" << endl;
 }
};
int main() {
 // Step 8: Demonstrate Function Overloading
 FunctionOverloading obj1;
 cout << "Function Overloading Demonstration:" << endl;
 obj1.display(5);
 obj1.display(3.14);
 obj1.display("Hello");
 cout << "\nFunction Overriding Demonstration:" << endl;
 
 // Step 9: Demonstrate Function Overriding
 Base* basePtr; // Base class pointer
 Derived obj2; // Derived class object
 basePtr = &obj2;
 basePtr->show(); // Calls Derived class’s overridden function due to polymorphism
 return 0;
}
Function Overloading Demonstration:

Integer: 5
Double: 3.14
String: Hello

Function Overloading Demonstration:
Derived Class Show Function

Explanation:
Step 1: Include Standard Library
• Include the <iostream> library to use input (cin) and output (cout) functions.
• Use the std namespace to avoid writing std:: before every standard function.
Part 1: Function Overloading
Step 2: Define a Class for Function Overloading
• Create a class named OverloadingDemo.
• Declare all member functions inside the class.
Step 3: Create Overloaded Functions
• Define multiple functions with the same name but different parameter lists.
• Function 1: Takes an integer and prints it.
• Function 2: Takes a double and prints it.
• Function 3: Takes two integers and prints both.
Step 4: Demonstrate Function Overloading in main()
• Create an object of OverloadingDemo.
• Call the overloaded functions with different arguments:
o Call the function with an integer.
o Call the function with a double.
o Call the function with two integers.
Part 2: Function Overriding
Step 5: Define a Base Class: Create a class named BaseClass. Define a function with a 
specific name, for example, showMessage(), inside this class.
Step 6: Define a Derived Class
• Create a class named DerivedClass that inherits from BaseClass.
• Define the same function (showMessage()) inside DerivedClass with different 
behavior.
Step 7: Demonstrate Function Overriding in main()
• Create an object of DerivedClass.
• Call showMessage() using the DerivedClass object to invoke the overridden function.
• If the function is called using a BaseClass pointer pointing to a DerivedClass object, 
the BaseClass version will be called unless the function is declared as virtual.
Step 8: Use Virtual Function (if needed)
• If the function in BaseClass is declared as virtual, the overridden function in 
DerivedClass will be called even when accessed through a BaseClass pointer.
Step 9: End of Program
• The program terminates after executing both function overloading and overriding 
Demonstration.

(DAA)
Aim:-To select the Nth Max/Min element in a list by using various algorithms and Compare
the efficiency of algorithms
##This function takes two inputs:
#lst: The list of numbers.
#n: The position of the max/min element we need to find.
def nth_max_min(lst, n):
#If n is larger than the number of elements in the list OR less than 1, the function returns an
error message.
if n > len(lst) or n < 1:
return "N is out of range"
lst.sort() # Sorting the list in ascending order Example: If the input list is [7, 3, 9, 1, 5, 12,
8], after sorting, it becomes:[1, 3, 5, 7, 8, 9, 12].
nth_min = lst[n - 1] # Nth minimum element Since Python indexing starts at 0, the Nth
smallest element is at index n-1.
nth_max = lst[-n] # Nth maximum element The Nth largest element can be accessed
using negative indexing (-n).
return nth_min, nth_max
# Example Usage
arr = [7, 3, 9, 1, 5, 12, 8]
n = 2 # Find 2nd min and 2nd max
result = nth_max_min(arr, n)
print(f"{n}th Min: {result[0]}, {n}th Max: {result[1]}")
#2nd High and 3rd lowest
numbers = [95, 88, 76, 100, 82, 90, 99, 70, 85, 91]
# Sort the list
numbers.sort()
print("sort list:",numbers)
# Get 2nd highest and 3rd lowest
second_highest = numbers[-2]
third_lowest = numbers[2]
print("2nd Highest:", second_highest)
print("3rd Lowest:", third_lowest)

......................................................................................................
DAA
def nth_max_min(lst, n):
    """
    This function returns the Nth minimum and Nth maximum elements in a list.
    
    Parameters:
    lst (list): The list of numbers
    n (int): The position of the min/max to find

    Returns:
    tuple: (Nth Min, Nth Max)
    """
    if n > len(lst) or n < 1:
        return "N is out of range"
    
    lst.sort()  # Sort the list in ascending order
    nth_min = lst[n - 1]    # Nth minimum element
    nth_max = lst[-n]       # Nth maximum element
    
    return nth_min, nth_max

# Example Usage
arr = [7, 3, 9, 1, 5, 12, 8]
n = 2
result = nth_max_min(arr, n)
print(f"{n}th Min: {result[0]}, {n}th Max: {result[1]}")
# Input list
numbers = [95, 88, 76, 100, 82, 90, 99, 70, 85, 91]

# Sort the list
numbers.sort()
print("Sorted list:", numbers)

# 2nd highest and 3rd lowest elements
second_highest = numbers[-2]  # Second last element
third_lowest = numbers[2]     # Third element (index 2)

print("2nd Highest:", second_highest)
print("3rd Lowest:", third_lowest)
....................................................................................................................................

OPP
#include <iostream>
using namespace std;

// Class demonstrating Function Overloading
class FunctionOverloading {
public:
    void display(int num) {
        cout << "Integer: " << num << endl;
    }

    void display(double num) {
        cout << "Double: " << num << endl;
    }

    void display(string text) {
        cout << "String: " << text << endl;
    }
};

int main() {
    cout << "Function Overloading Demonstration:" << endl;
    
    FunctionOverloading obj1;
    obj1.display(5);           // Calls int version
    obj1.display(3.14);        // Calls double version
    obj1.display("Hello");     // Calls string version

    return 0;
}
#include <iostream>
using namespace std;

// Base class with virtual function
class Base {
public:
    virtual void show() {
        cout << "Base Class Show Function" << endl;
    }
};

// Derived class overriding show()
class Derived : public Base {
public:
    void show() override {
        cout << "Derived Class Show Function" << endl;
    }
};

int main() {
    cout << "Function Overriding Demonstration:" << endl;

    Base* basePtr;
    Derived obj2;
    basePtr = &obj2;

    basePtr->show();  // Calls Derived's show() due to virtual function

    return 0;
}

