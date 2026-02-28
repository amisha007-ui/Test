# Test
Python_test
class Flight:
    
    def _init_(self, flight_no, source, destination, base_fare):
        self.flight_no = flight_no
        self.source = source
        self.destination = destination
        self.base_fare = base_fare

    # b) get_flight_info method
    def get_flight_info(self):
        return f"Flight Number: {self.flight_no}, Source: {self.source}, Destination: {self.destination}"

    # c) calculate_fare method (method overloading style using default parameter)
    def calculate_fare(self, passenger_count, discount_percent=0):
        total_fare = self.base_fare * passenger_count
        
        if discount_percent > 0:
            total_fare = total_fare - (total_fare * discount_percent / 100)
        
        return total_fare

    # e) update_route method using default arguments
    def update_route(self, new_destination, new_source=None):
        if new_source is None:
            self.destination = new_destination
        else:
            self.source = new_source
            self.destination = new_destination


# d) Write code to:

# Create one Flight object
flight1 = Flight("AI203", "Bangalore", "Delhi", 4500)

# Call calculate_fare()

# Only passenger count
fare1 = flight1.calculate_fare(3)
print("Total Fare (No Discount):", fare1)

# Passenger count + discount
fare2 = flight1.calculate_fare(3, 10)
print("Total Fare (With Discount):", fare2)

# Test update_route
flight1.update_route("Mumbai")
print(flight1.get_flight_info())

flight1.update_route("Chennai", "Hyderabad")
print(flight1.get_flight_info())



2nd : 

flight_no = "AI203"
base_fare = "4500.75"
tax_percent = "5"
seat_numbers = "12A,12B,14C,15D"
is_international = "True"


# a) Convert base_fare and tax_percent and calculate final fare

base_fare = float(base_fare)
tax_percent = float(tax_percent)

final_fare = base_fare + (base_fare * tax_percent / 100)
print("Final Fare:", final_fare)


# b) Convert seat_numbers string into list

seat_list = seat_numbers.split(",")
print("Seat List:", seat_list)


# c) Convert list into set

seat_set = set(seat_list)
print("Seat Set:", seat_set)


# d) Convert is_international into boolean

is_international = True if is_international == "True" else False
print("Is International:", is_international)


# e) Create dictionary flight_summary with type conversion

flight_summary = {
    "flight_no": flight_no,                
    "final_fare": int(final_fare),          
    "seat_numbers": tuple(seat_list)       
}

print("Flight Summary:", flight_summary)


3rd.


class Product:
    def _init_(self, id, name):
        self.id = id
        self.name = name

    def display(self):
        print("Product ID:", self.id)
        print("Product Name:", self.name)


class ABC(Product):
    def _init_(self, id, name, count, category):
        # Calling parent class constructor
        super()._init_(id, name)
        self.count = count
        self.category = category

    def display(self):
        print("Product ID:", self.id)
        print("Product Name:", self.name)
        print("Count:", self.count)
        print("Category:", self.category)
        print("-------------------")


item1 = ABC(78, "Amul", 50, "Butter")
item2 = ABC(78, "Amul", 90, "Milk")
item3 = ABC(78, "Amul", 56, "Choco")


item1.display()
item2.display()
item3.display()
