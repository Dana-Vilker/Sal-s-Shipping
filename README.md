# Sal-s-Shipping
Codecademy's Sal's Shipping Python Coding Project

#Write a function for the cost of ground shipping. This function should take one parameter, weight, and return the cost of shipping a package of that weight.

def cost_ground_shipping(weight):
  if weight <= 2:
    cost = (1.5 * weight) + 20
    return cost
  elif 2 < weight <= 6:
    cost = (3.00 * weight) + 20
    return cost
  elif 6 < weight <= 10:
    cost = (4.00 * weight) + 20
    return cost
  else:
    cost = (4.75 * weight) + 20
    return cost

#Test your function:
  
print(cost_ground_shipping(8.4))

#Create a variable for the cost of premium groud shipping:

premium = 125.00

#Write a function for the cost of drone shippin, this function sohuld take one parameter, weight, and return the cost of shipping a package of that weight:

def cost_drone_shipping(weight):
  if weight <= 2:
    cost = weight * 4.50
    return cost
  elif 2 < weight <= 6:
    cost = weight * 9.00
    return cost
  elif 6 < weight <= 10:
    cost = weight * 12.00
    return cost
  else:
    cost = weight * 14.25
    return cost
  
#Test your function:

print(cost_drone_shipping(1.5))

#Write a function that takes one parameter, weight,and prints a statement that tells the user the shipping method that is cheapest, how much it would cost to ship a package of said weight using this method:

def best_shipping(weight):
  if (cost_drone_shipping(weight) >= 125.00) and (cost_ground_shipping(weight) >= 125.00):
    return "The cheapest shipping method is Premium Shipping, for $125.00"
  elif cost_drone_shipping(weight) < cost_ground_shipping(weight):
    return ("The cheapest shipping method is drone shipping, for " + str(cost_drone_shipping(weight)) + " dollars")
  elif cost_drone_shipping(weight) > cost_ground_shipping(weight):
    return ("The cheapest shipping method is ground shipping, for " + str(cost_ground_shipping(weight)) + " dollars")
  else:
    return "Drone and ground shipping will cost the same"
  
#Test your function:

print(best_shipping(4.8))

print(best_shipping(41.5))
