from abc import ABC, abstractmethod
class Factory(ABC):
    
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model
        
        @abstractmethod
        def display_info(self):
            pass 
        
class Car(Factory):
    
    def __init__(self, brand, model, engine):
        super().__init__(brand, model)
        self.engine = engine 
        
    def display_info(self):
        return f"Car: {self.brand} {self.model}, Engine: {self.engine}"
        

class Bike(Factory):
    
    def __init__(self, brand, model, type_bike):
        super().__init__(brand, model)
        self.type_bike = type_bike
    
    
    def display_info(self):
        return f"Bike: {self.brand} {self.model}, Type: {self.type_bike}"
        
class ElectricCar(Car):
    
    def __init__(self, brand, model, battery_capacity):
        super().__init__(brand, model, "Electric")
        self.battery_capacity = battery_capacity
        
        
car = Car("Toyota", "Camry", "V6")
bike = Bike("TVS", "RR310", "Sport")
ev = ElectricCar("Tesla", "Model 3", 75)

for factory in (car, bike, ev):
    print(factory.display_info())
