# EXERCISE-OOP-SYNTAX-EXERCISE-PART-2

## Disclaimer: This exercise was Created by Udacity (AWS Machine Learning Foundations Course) (Solution of the exercise and adaptation as a repository: Andrés R. Bücheli.)

Writing classes in Python. 

# Pants class
Write a Pants class with the following characteristics:

* the class name should be Pants
* the class attributes should include
    * color
    * waist_size
    * length
    * price
* the class should have an init function that initializes all of the attributes
* the class should have two methods
    * change_price() a method to change the price attribute
    * discount() to calculate a discount

<pre><code>
### TODO:
#   - code a Pants class with the following attributes
#   - color (string) eg 'red', 'yellow', 'orange'
#   - waist_size (integer) eg 8, 9, 10, 32, 33, 34
#   - length (integer) eg 27, 28, 29, 30, 31
#   - price (float) eg 9.28

### TODO: Declare the Pants Class 

### TODO: write an __init__ function to initialize the attributes

### TODO: write a change_price method:
#    Args:
#        new_price (float): the new price of the shirt
#    Returns:
#        None

### TODO: write a discount method:
#    Args:
#        discount (float): a decimal value for the discount. 
#            For example 0.05 for a 5% discount.
#
#    Returns:
#        float: the discounted price

class Pants:
    
    def __init__(self, pants_color, pants_waist_size, pants_length, pants_price):
        self.color = pants_color
        self.waist_size = pants_waist_size
        self.length = pants_length
        self.price = pants_price
        
    def change_price(self, new_price):
        
        self.price = new_price
        
    def discount(self, discount):
        
        return self.price*(1-discount)
</pre></code>
