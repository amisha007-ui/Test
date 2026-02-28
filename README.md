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
