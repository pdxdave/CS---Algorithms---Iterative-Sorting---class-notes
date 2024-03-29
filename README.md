# CS---Algorithms---Iterative-Sorting---class-notes
CS---Algorithms---Iterative-Sorting---class-notes

### Time Complexity.  What is it?
How does the performance of your code scale based on the size of your inputs?

```
0(n!) 0(2^n)
                0(n^2) // like a double for loop
                      
                           
                           
                           0(n log n)
                           
                            
                            
                              0(n) // like 1:1. One operation per nth item
                              
                              0(log n), 0(1) // if steps get halfed w/each interation that's logarithmic                
```

### Challenge question: Do a linear search usign Python
```
def search(numbers, searchFor):
    for i in range(len(numbers)):
        if searchFor == numbers[i]:
            print("number is found")
            break
    else:
        print("number is not found")


numbers = [6,7,2,1,0,9,8]
searchFor = 1
search(numbers, searchFor)

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

### This is a binary search

TIME COMPLEXITY: 0(log n)


This is the divide and conquer approach and is dependent upon the list being sorted.  It works like this. Once the low and high point of the list are identified, the list will be divided.  This is done by adding the low(int 0) and high(int 17) together, then dividing the result.  This creates a starting point for the search.  So in this case, the mid point is integer 8, which would be the value 23.  The first pass will see if the number input by the user is exactly the right number.  If not, it will see if the number input is less than the midpoint.  If so, then it drops all the numbers right of the midpoint.  If not, it drops all of the numbers left of the midpoint.  In this case, let's go with the former (all of the numbers to the right are dropped) as the key I entered is 7.  Now the low and high point are reset. The low int is 0, and the high int is 7.  Once again, they will be added, then divided to find the middle point.  The middle point is now three, and once again it is checking to see if the key I entered is associated with an int larger than 3.
```
2log(n)

def binary_search(list1, key):
    low = 0
    high = len(list1) -1
    Found = False
    while low <= high and not Found:
        mid = (low + high) // 2
        if key == list1[mid]:
            Found = True
        elif key < list1[mid]:
            high = mid - 1
        else:
            low = mid + 1
    if Found == True:
        print("Key is found")
    else:
        print("Key is not found")
    
    
list1 = [3,5,7,22,3,5,88,76,54,63,23,43,56,43,78,11,4,28]
list1.sort()
key = int(input("Input a number to search for: "))
binary_search(list1, key)
```

### This is Insertion Sorting
```
0(n^2)  // We have two loops.  A 'for' and a 'while'. 

def insertion_sort(list):
    # starting at index 1 allows the sort to compare index 1 to 0,
    # 0 being to its immediate left
    for index in range(1, len(list)):
       
        value = list[index]
        
        i = index - 1
        
        while i >= 0:
            if value < list[i]:
                list[i+1] = list[i]
                list[i] = value
                i = i - 1
            else:
                break

a = [2,7,3,9]
insertion_sort(a)
```
