# Inheritance

class Employee:
    increment = 1.5
    no_of_emp = 0
    def __init__(self, fname, lname, salary):
        self.fname = fname
        self.lname = lname
        self.salary = salary
        Employee.no_of_emp += 1
        
    def increse(self):
        self.salary = self.salary + self.increment
     
    @classmethod
    def change_increment(cls, amount):
        cls.increment = amount
        
class Programmer(Employee):
    def __init__(self, fname, lname, salary, proglang, exp):
        super().__init__(fname, lname, salary)
        self.proglang = proglang
        self.exp = exp
    
    def increse(self):
        self.salary = int(self.salary * (self.increment+0.3))
        return self.salary
    
salman = Programmer("salman", "shaikh", 12000, "python", "1yr")
azaz = Programmer("azaz", "ansari", 44000, "java", "2yr")

print(salman.salary)
print(azaz.proglang)

salman.increse()
print(salman.salary)
