# Week-5-Assignment-1
# Base class
class Smartphone:
    def __init__(self, brand, model, price):
        self.brand = brand
        self.model = model
        self.__price = price  # Private attribute (Encapsulation)

    def get_info(self):
        return f"{self.brand} {self.model} - Price: ${self.__price}"

    def set_price(self, new_price):
        if new_price > 0:
            self.__price = new_price
        else:
            print("Invalid price. Must be greater than 0.")

# Subclass (Inheritance)
class Smartwatch(Smartphone):
    def __init__(self, brand, model, price, battery_life):
        super().__init__(brand, model, price)
        self.battery_life = battery_life

    def get_info(self):
        return f"{self.brand} {self.model} - Battery Life: {self.battery_life} hours"

# Creating objects
phone = Smartphone("Apple", "iPhone 15", 999)
watch = Smartwatch("Samsung", "Galaxy Watch 6", 299, 48)

# Accessing methods
print(phone.get_info())  # Accessing base class method
phone.set_price(1099)    # Updating price
print(phone.get_info())  # Checking updated price

print(watch.get_info())  # Accessing overridden method in subclass
