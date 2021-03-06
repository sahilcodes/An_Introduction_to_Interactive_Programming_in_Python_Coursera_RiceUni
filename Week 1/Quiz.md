# Question 1
  An `if` statement can have at most how many `else` parts?

### Answer
    1

----
# Question 2
  Consider the Boolean expression `not (p or not q)`. Give the four following values in order, separated only by spaces:

    The value of the expression when p is True, and q is True.  
    The value of the expression when p is True, and q is False.  
    The value of the expression when p is False, and q is True.  
    The value of the expression when p is False, and q is False.  

Remember, each of the four results you provide should be `True` or `False` with the proper capitalization.

### Answer
    False False True False  

----
# Question 3
  A common error for beginning programmers is to confuse the behavior of `print` statements and `return` statements.  

* `print` statements can appear anywhere in your program and print a specified value(s) in the console.

Note that executing a `print` statement inside a function definition does not return a value from the function.  

* `return` statements appear inside functions. The value associated with the `return` statement is substituted for the expression that called the function.

Note that executing a `return` statement terminates execution of the function definition immediately and any statements in the function definition following the `return` statement are ignored.

As an example to illustrate these points, consider the following piece of code:  

    def do_stuff():  
      print "Hello world"  
      return "Is it over yet?"  
      print "Goodbye cruel world!"

    print do_stuff()  

Which of the following is the console output that results from executing this piece of code? While it is trivial to solve this question by cutting and pasting this code into CodeSkulptor, we suggest that you first attempt this problem by attempting to execute this code in your mind.  

### Answer  
    Hello world  
    Is it over yet?  

----
# Question 4
  Given a non-negative integer n, which of the following expressions computes the ten's digit of n? For example, if n is 123, then we want the expression to evaluate to 2.

### Answer
    (n % 100 - n % 10) / 10  
    ((n - n % 10) / 10) % 10

### Code and Explanation
    n = 123
    a = (n % 100 - n % 10) / 10
    b = ((n - n % 10) / 10) % 10
    c = (n - n % 10) / 10
    print a,b,c

    # Output
      2 2 12

    1) (n % 100 - n % 10) / 10 : This expression computes the ten's digit correctly.  
    2) ((n - n % 10) / 10) % 10 : This expression computes the ten's digit correctly.
    3) (n - n % 10) / 10 : This expression just truncates the one's digit.  

----
# Question 5
  The function calls `random.randint(0, 10)` and `random.randrange(0, 10)` generate random numbers in different ranges. What number can be generated by one of these functions, but not the other?  

### Answer
    10

----
# Question 6
  Implement the mathematical function `f(x) = (-5)*x^5 + (69)*x^2 - 47` as a Python function. Then use Python to compute the function values `f(0)`, `f(1)`, `f(2)`, and `f(3)`. Enter the maximum of these four numbers.

### Answer
    69

### Code
      import math

      def f(x):
      return (-5 * math.pow(x, 5)) + (69 * math.pow(x, 2)) - 47

      print f(0), f(1), f(2), f(3)
      print max(f(0), f(1), f(2), f(3))

      # Output
        -47.0 17.0 69.0 -641.0
        69.0

----
# Question 7
  When investing money, an important concept to know is compound interest. The equation `FV = PV (1+rate)^periods` relates the following four quantities.

  The present value (PV) of your money is how much money you have now. The future value (FV) of your money is how much money you will have in the future. The nominal interest rate per period (rate) is how much interest you earn during a particular length of time, before accounting for compounding. This is typically expressed as a percentage. The number of periods (periods) is how many periods in the future this calculation is for. Finish the following code, run it, and submit the printed number. Provide at least four digits of precision after the decimal point.

    def future_value(present_value, annual_rate, periods_per_year, years):  
      rate_per_period = annual_rate / periods_per_year  
      periods = periods_per_year * years      
      # Put your code here.  
    print "$1000 at 2% compounded daily for 3 years yields $", future_value(1000, .02, 365, 3)

  Before submitting your answer, test your function on `future_value(500, .04, 10, 10)` and it should return 745.317442824.  

### Answer
    1061.83480113

### Code
      import math

      def future_value(present_value, annual_rate, periods_per_year, years):
          rate_per_period = annual_rate / periods_per_year
          periods = periods_per_year * years
          return present_value * math.pow(1 + rate_per_period, periods)

      print "$500 at 4% compounded daily for 10 years yields $", future_value(500, .04, 10, 10)
      print "$1000 at 2% compounded daily for 3 years yields $", future_value(1000, .02, 365, 3)

      # Output
        $500 at 4% compounded daily for 10 years yields $ 745.317442824
        $1000 at 2% compounded daily for 3 years yields $ 1061.83480113

----
# Question 8
  There are several ways to calculate the area of a regular polygon. Given the number of sides, `n`, and the length of each side, `s`, the polygon's area is `(1/4 * n * (s^2)) / tan(pi/n)`. For example, a regular polygon with 5 sides, each of length 7 inches, has area 84.3033926289 square inches. Write a function that calculates the area of a regular polygon, given the number of sides and length of each side. Submit the area of a regular polygon with 7 sides each of length 3 inches. Enter a number (and not the units) with at least four digits of precision after the decimal point.

### Answer
    32.705211996

### Code
      def area_regular_polygon(no_of_sides, length_of_each_side):
          a = math.tan(math.pi / no_of_sides)
          b = (no_of_sides) * math.pow(length_of_each_side, 2)
          c = b / a
          return c / 4

      print area_regular_polygon(5, 7)
      print area_regular_polygon(7, 3)

      # Output
        84.3033926289
        32.705211996

----
# Question 9
  Running the following program results in the error SyntaxError: bad input on line 8 ('return'). Which of the following describes the problem?  

    def max_of_2(a, b):  
      if a > b:  
        return a  
      else:  
        return b  

    def max_of_3(a, b, c):  
    return max_of_2(a, max_of_2(b, c))  

### Answer
    Incorrect indentation

### Explanation
    The body of the function definition for max_of_3() should be indented, but it is not.  

----
# Question 10
  The following code has a number of syntactic errors in it. The intended math calculations are correct, so the only errors are syntactic. Fix the syntactic errors. Once the code has been fully corrected, it should print out two numbers. The first should be 1.09888451159. Submit the second number printed in CodeSkulptor. Provide at least four digits of precision after the decimal point.  

    define project_to_distance(point_x point_y distance):  
      dist_to_origin = math.square_root(pointx ** 2 + pointy ** 2)      
      scale == distance / dist_to_origin  
      print point_x * scale, point_y * scale
       
    project-to-distance(2, 7, 4)  

### Answer
    3.84609579056

### Code
      import math

      def project_to_distance(point_x, point_y, distance):
          dist_to_origin = math.sqrt(point_x ** 2 + point_y ** 2)    
          scale = distance / dist_to_origin
          print point_x * scale, point_y * scale

      project_to_distance(2, 7, 4)

      # Output
        1.09888451159 3.84609579056

----
