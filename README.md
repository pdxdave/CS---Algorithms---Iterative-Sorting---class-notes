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
so a set twice the size will take twice the time. The input is size (n).  In this
case three animals.

** For loop is a good indicator of an 0(n) operation

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
  
  
# Given the name of an animal
# Return the animal's index if that animal is in the list, else -1

def findAnimal(animal_name):
  animal_index = 0
  for animal in animals:
    if animal == animal_name:
      return animal_index
    animal_index += 1
  return -1

  

```
```

An algorithm is said to run in logarithmic time if its time execution is proportional to the square of the input size. Examples: bubble sort, selection sort, insertion sort.

** Notice two For loops

######
0(n^2)
######

# Print a list of all possible animal pairs

def printAnimalPairs():
  for animal in animals:
    for animal2 in animals:
      print(f"{animal} - {animal2}")

```
```
######
0(n^3)
######

** Notice the three For loops

# Print a list of all possible animal triples

def printBookTriples():
  for animal in animals:
    for anmial2 in animals:
      for animal3 in animals:
        print(f"{animal1} - {animal2} - {animal3}")

```
```
######
0(2^n)
######

# Given a list,
# Return a list of all possible combinations of animals

** Hint. Getting all possible combinations is typical of this time complexity

def getListOfAnimalCombos(1):
  list_length = len(l)
  if list_length == 0:
    return [ [] ]
  else:
    animalCombos = []
    previousCombos = getListofAnimalCombos(l[1:])
    for combo in previousCombos:
      animalCombos.append(combo)
      animalCombos.append(combo + [l[0]] )
    return animalCombos
```
```
######
0(n!)
######

# Given a list,
# Return a list of all possible arrangements of list items

def getAllArrangements(l):
  list_length = getLengthOfList(l)
  if list_length <= 1:
    return [l]
  else:
    arrangements = []
    previousArrangements = getAllArrangements(l[1:])
    for previousArrangement in previousArrangements:
      for i in range(getLengthOfList(previousArrangement) + 1)
        arrangement.append(previousArrangement[1:] + [l[0]]....

```
#### How can these do the same thing, but with different time complexities?
```
# 0(n)
def getLengthOfList(l):
  list_length = 0
  for i in l:
    list_length += 1
  return list_length
  
# 0(1)
def betterGetLengthOfList(l):
  return len(l)
  
So how do we count n items in constant time?
Amortization.

```

## Sorting

#### Q: Why is sorting so important?  A: It's tied to searching
