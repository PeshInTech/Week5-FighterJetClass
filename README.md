# Week5-FighterJetClass

**Assignment 1: Design Your Own Class! 🏗️**

Create a class representing anything you like (a Smartphone, Book, or even a Superhero!).
Add attributes and methods to bring the class to life!
Use constructors to initialize each object with unique values.
Add an inheritance layer to explore polymorphism or encapsulation.

# Base FighterJet class
class FighterJet:
    def __init__(self, model, speed, range, armament):
        self.model = model
        self.speed = speed  
        self.range = range  
        self.__armament = armament  # Encapsulated attribute
    
    def fly(self):
        print(f"{self.model} is flying at Mach {self.speed}.")

    def attack(self):
        print(f"{self.model} attacking with {self.__armament}.")

    def refuel(self):
        print(f"{self.model} is refueling.")

    # Encapsulated method
    def __maintenance_check(self):
        print(f"{self.model} is undergoing a maintenance check.")

    # Public method to access private method
    def maintenance(self):
        self.__maintenance_check()

# Derived class for stealth jets
class StealthJet(FighterJet):
    def __init__(self, model, speed, range, armament, stealth_coating):
        super().__init__(model, speed, range, armament)
        self.stealth_coating = stealth_coating

    def evade_radar(self):
        print(f"{self.model} is evading radar with {self.stealth_coating} coating.")

# Creating objects
jet1 = FighterJet("F-16 Falcon", 2.0, 2200, "missiles and bombs")
jet2 = StealthJet("F-22 Raptor", 2.25, 1800, "advanced missiles", "low radar signature")

jet1.fly()
jet1.attack()
jet1.maintenance()  # Accessing encapsulated method

jet2.fly()
jet2.attack()
jet2.evade_radar()

**Expected Output**
F-16 Falcon is flying at Mach 2.0.
F-16 Falcon attacking with missiles and bombs.
F-16 Falcon is undergoing a maintenance check.
F-22 Raptor is flying at Mach 2.25.
F-22 Raptor attacking with advanced missiles.
F-22 Raptor is evading radar with low radar signature coating.


**Activity 2: Polymorphism Challenge! 🎭**

Create a program that includes animals or vehicles with the same action (like move()). However, make each class define move() differently (for example, Car.move() prints "Driving" 🚗, while Plane.move() prints "Flying" ✈️).

# Base Vehicle class
class Vehicle:
    def move(self):
        print("Vehicle is moving.")

# Car class
class Car(Vehicle):
    def move(self):
        print("Car is driving 🚗")

# Plane class
class Plane(Vehicle):
    def move(self):
        print("Plane is flying ✈️")

# Ship class
class Ship(Vehicle):
    def move(self):
        print("Ship is sailing 🚢")

# Creating objects
vehicle1 = Car()
vehicle2 = Plane()
vehicle3 = Ship()

# Demonstrate polymorphism
for vehicle in (vehicle1, vehicle2, vehicle3):
    vehicle.move()

**Expected Result**
Car is driving 🚗
Plane is flying ✈️
Ship is sailing 🚢

