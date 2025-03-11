#OOPs concepts 

# Abstraction: Creating an abstract class
class Vehicle(ABC):
    def __init__(self, brand, model):
        self.brand = brand  # Public attribute
        self._model = model  # Protected attribute

    @abstractmethod
    def display_info(self):
       
# Encapsulation: Creating a class with private variables
class Car(Vehicle):
    def __init__(self, brand, model, engine):
        super().__init__(brand, model)
        self.__engine = engine  # Private attribute

    def display_info(self):
        return f"Car: {self.brand} {self._model}, Engine: {self.__engine}"

# Inheritance: Bike inherits from Vehicle
class Bike(Vehicle):
    def __init__(self, brand, model, type_of_bike):
        super().__init__(brand, model)
        self.type_of_bike = type_of_bike

    def display_info(self):
        return f"Bike: {self.brand} {self._model}, Type: {self.type_of_bike}"

# Multiple Inheritance: ElectricCar inherits from Car and Vehicle
class ElectricCar(Car):
    def __init__(self, brand, model, battery_capacity):
        super().__init__(brand, model, "Electric")
        self.battery_capacity = battery_capacity

    # Polymorphism: Overriding the display_info method
    def display_info(self):
        return f"Electric Car: {self.brand} {self._model}, Battery: {self.battery_capacity} kWh"

# Creating objects
car = Car("Toyota", "Camry", "V6")
bike = Bike("Yamaha", "R15", "Sport")
ev = ElectricCar("Tesla", "Model 3", 75)

# Displaying details using polymorphism
for vehicle in (car, bike, ev):
    print(vehicle.display_info())
