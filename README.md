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

# Run the code cell below to check results
If you run the next code cell and get an error, then revise your code until the code cell doesn't output anything.

<pre><code>
def check_results():
    pants = Pants('red', 35, 36, 15.12)
    assert pants.color == 'red'
    assert pants.waist_size == 35
    assert pants.length == 36
    assert pants.price == 15.12
    
    pants.change_price(10) == 10
    assert pants.price == 10 
    
    assert pants.discount(.1) == 9
    
    print('You made it to the end of the check. Nice job!')

check_results()
</code></pre>

# SalesPerson class
The Pants class and Shirt class are quite similar. Here is an exercise to give you more practice writing a class. <strong>This exercise is trickier than the previous exercises</strong>.

Write a SalesPerson class with the following characteristics:

* the class name should be SalesPerson
* the class attributes should include
   * first_name
   * last_name
   * employee_id
   * salary
   * pants_sold
   * total_sales
* the class should have an init function that initializes all of the attributes
* the class should have four methods
   * sell_pants() a method to change the price attribute
   * calculate_sales() a method to calculate the sales
   * display_sales() a method to print out all the pants sold with nice formatting
   * calculate_commission() a method to calculate the salesperson commission based on total sales and a percentage
   
<pre><code>
### TODO:
#   Code a SalesPerson class with the following attributes
#   - first_name (string), the first name of the salesperson
#   - last_name (string), the last name of the salesperson
#   - employee_id (int), the employee ID number like 5681923
#   - salary (float), the monthly salary of the employee
#   - pants_sold (list of Pants objects), 
#            pants that the salesperson has sold 
#   - total_sales (float), sum of sales of pants sold

### TODO: Declare the SalesPerson Class 

### TODO: write an __init__ function to initialize the attributes
###    Input Args for the __init__ function:
#        first_name (str)
#        last_name (str)
#        employee_id (int)
# .      salary (float)
#
# You can initialize pants_sold as an empty list
# You can initialize total_sales to zero.
#
###

### TODO: write a sell_pants method:
#
#    This method receives a Pants object and appends
#    the object to the pants_sold attribute list
#
#    Args:
#        pants (Pants object): a pants object
#    Returns:
#        None

### TODO: write a display_sales method:
#    
#    This method has no input or outputs. When this method 
#    is called, the code iterates through the pants_sold list
#    and prints out the characteristics of each pair of pants
#    line by line. The print out should look something like this
#
#   color: blue, waist_size: 34, length: 34, price: 10
#   color: red, waist_size: 36, length: 30, price: 14.15
#
#
#
###

### TODO: write a calculate_sales method:
#      This method calculates the total sales for the sales person.
#      The method should iterate through the pants_sold attribute list
#      and sum the prices of the pants sold. The sum should be stored
#      in the total_sales attribute and then return the total.
#      
#      Args:
#        None
#      Returns:
#        float: total sales
#
###  


### TODO: write a calculate_commission method:
#
#   The salesperson receives a commission based on the total
#   sales of pants. The method receives a percentage, and then
#   calculate the total sales of pants based on the price,
#   and then returns the commission as (percentage * total sales)
#
#    Args:
#        percentage (float): comission percentage as a decimal
#
#    Returns:
#        float: total commission
#
#
###

class SalesPerson:
    
    def __init__(self, first_name, last_name, employee_id, salary):
        self.first_name = first_name
        self.last_name = last_name
        self.employee_id = employee_id
        self.salary = salary
        self.pants_sold = []
        self.total_sales = 0
        
    def sell_pants(self, pants_object):
    
        self.pants_sold.append(pants_object)
        
    def display_sales(self):
        for pants in self.pants_sold:
            print('color: {}, waist_size: {}, length: {}, price: {}'\
                  .format(pants.color, pants.waist_size, pants.length, pants.price))
    
    def calculate_sales(self):
        total = 0
        for pants in self.pants_sold:
            total += pants.price
            
        self.total_sales = total
        
        return total
    
    def calculate_commission(self, percentage):
        sales_total = self.calculate_sales()
        return sales_total * percentage 
</code></pre>

# Run the code cell below to check results
If you run the next code cell and get an error, then revise your code until the code cell doesn't output anything.

<pre><code>
def check_results():
    pants_one = Pants('red', 35, 36, 15.12)
    pants_two = Pants('blue', 40, 38, 24.12)
    pants_three = Pants('tan', 28, 30, 8.12)
    
    salesperson = SalesPerson('Amy', 'Gonzalez', 2581923, 40000)
    
    assert salesperson.first_name == 'Amy'
    assert salesperson.last_name == 'Gonzalez'
    assert salesperson.employee_id == 2581923
    assert salesperson.salary == 40000
    assert salesperson.pants_sold == []
    assert salesperson.total_sales == 0
    
    salesperson.sell_pants(pants_one)
    salesperson.pants_sold[0] == pants_one.color
    
    salesperson.sell_pants(pants_two)
    salesperson.sell_pants(pants_three)
    
    assert len(salesperson.pants_sold) == 3
    assert round(salesperson.calculate_sales(),2) == 47.36
    assert round(salesperson.calculate_commission(.1),2) == 4.74
    
    print('Great job, you made it to the end of the code checks!')
    
check_results()
</code></pre>

# Check display_sales() method
If you run the code cell below, you should get output similar to this:

      color: red, waist_size: 35, length: 36, price: 15.12
      color: blue, waist_size: 40, length: 38, price: 24.12
      color: tan, waist_size: 28, length: 30, price: 8.12
      
<pre><code>
pants_one = Pants('red', 35, 36, 15.12)
pants_two = Pants('blue', 40, 38, 24.12)
pants_three = Pants('tan', 28, 30, 8.12)

salesperson = SalesPerson('Amy', 'Gonzalez', 2581923, 40000)

salesperson.sell_pants(pants_one)    
salesperson.sell_pants(pants_two)
salesperson.sell_pants(pants_three)

salesperson.display_sales()
</code></pre>

# Solution of the exercise and adaptation as a Repository: Andrés R. Bücheli.
