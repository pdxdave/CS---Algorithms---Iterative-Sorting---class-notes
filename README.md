# CS---Algorithms---Iterative-Sorting---class-notes
CS---Algorithms---Iterative-Sorting---class-notes

### Time Complexity.  What is it?
How does the performance of your code scale based on the size of your inputs?

```
0(n!) 0(2^n)
                0(n^2)
                      
                           
                           
                           0(n log n)
                           
                            
                            
                              0(n)
                              
                              0(log n), 0(1)                 
```

```
animals = ['bird', 'cat', 'fish']

O(1) means that it takes a constant time, like 14 nanoseconds, or three minutes 
no matter the amount of data in the set. 

######
0(1)
######

# Return the name of all animals
def getAnimals();
  return animals

```

```
animals = ['bird', 'cat', 'fish']

O(n) means it takes an amount of time linear with the size of the set, 
so a set twice the size will take twice the time.

######
0(n)
######

# Return the name of all animals

def getAnimals();
  return animals
  
 
# Returns each animal with all letters lowercase

def getLowerCaseAnimals():
  lowercase_animals = animals
  animal_index = 0
  for animal in animals:
    lowercase_animals[animal_index] = lowercase_animals[animal_index].lower()
    animal_index += 1
  return lowercase_animals
  
  
# Given the name of an animal
# Return True if that animal is in the list, False otherwise

def hasAniaml(animal_name):
  for animal in animals:
    if animal == animal_name:
      return True
  return False
  

```

