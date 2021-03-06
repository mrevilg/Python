# Python Coding Language
Python code base for individual and ongoing projects

## Basic Concepts
| Operator Precedence | Explanations |
| ------------- | ------------- |
| **  | To the power of  |
| -X  | Negative number  |
| * / %  | Multiply, Divide, Modulus or Remainder |
| + -  | Add, Minus  |
| *Boolean* | ------------- |
| not  | First  |
| and | Next  |
| or  | Last  |

 "#" for a comment line
 
 "\n" is a string, needs '' or ""
 
input function will always return a string unless: int('*prompt*') * 7 etc to generate total, not string.

len() is a counting function, not an indexing 

## Style Best Practices
### PEP 8 Recommendations
#### Indentation - 4 spaces, not 4 tabs
#### Line Length - 79 Char, 72 Char for Comments
#### Blank Lines - to indicate blocks of code visually

##

#### *Variables*
- Start with a letter or underscore
- Avoid the following keywords

| False | None | True  |  |   |  | |  |
| ------------- | ------------- |------------- | ------------- |------------- | ------------- |------------- | ------------- |
| and | as | assert |break |class |continue |def |del |
| elif | else | except |global |is |or |try |break |
| finally | for | if |lambda |pass |while |import |nonlocal |
|raise |with |in | not | return | yield|

### *Methods/Functions*
#### *String Methods*
- len or str (variablename), etc...
- len(), str(),

#### *'dot' Methods*
- variablename.lower(), variablename.upper() etc...
- .lower(), .upper(),
- .title() ...Cap first letter of each word in string


#### *'whitespacing' Methods*
- print("\tPython") tabspace then string
- print("\nPython") carriage Rtn then string
- variablename.rstrip() temp trim on right of var
- variablename.lstrip() temp trim on left of var
- variablename.strip() temp trim on left/right of var
- variablename = variablename.strip() perm trim on left/right of var

When using the result of an int (as a standalone variable) within the result of a string (concatenation of int+str) you must set how the int is to be used int/str e.g. :
  ```python
    age = 23
    print "Happy " + str(age) + "rd Birthday!"
  ```
##
#### *List Methods and Modifications*
Python lists are 'indexed' - they start at 0, using [-1] returns last item
  ```python
  bicycles = ['trek', 'cannondale', 'redline', 'specialized']
  print bicycles
  ```
- variable name[x] = new_content This will replace the index 'x' with the new value
- .append('newvalue') ...adds new value to end of list, or can be used to 'overflow'
- .insert(index, 'value') ... adds the new value at the noted index
- del variablename[x] = removal of that index's value
new_variablename = variablename.pop(x)... takes last index value and adds to new variable, or use 'x' index, Pop REMOVES values
- variablename.remove('actualvalue')... will search and remove noted value, first instance. Need loop for multiple.
- variable.sort()... permanently sorts the list, can do str or int, must define to concatenate mixed
- variable.sort(reverse=True)... perm reverse
- sorted(variablename)... temp sorting of list variable, can accept reverse=True argument
- variablename.reverse()... reverses the list as-is, perm.

#### *Lists and Loops*
 ```python
    variables = ['var_1', 'var_2', 'var_3',]
    for variable in variables:
        print(variable)
  ```
- Colon and subsequent line indentation associate that indented line *with the loop*
 ```python
    for value in range (1,5):
        print(value)
 ```
- range (x,y)... gives the tone stpes between each number
- variablename = list(range(x,y))... creates a list of numbers within the x/y range
- variablename = list(range(x,y,z))... x is start of range, y is end of range, z is step
```python
    squares = []
    for value in range (1,11):
        squares.append(value**2)
        
    print(squares)
 ```
 [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
 
 - If we use the now squares variable, min/max/sum are 1/100/385 respectivley 
 ```python
    squares = [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
    print(min(squares))
    print(max(squares))
    print(sum(squares))
 ```
*List comprehensions* are an embedded syntax in the list itself eg:
 ```python
    squares = [value**2 for value in range(1,11)]
    print(squares)
 ```
Slicing a list variablename = [1,2,3,4,5] print(variablename[x:y])... would print those index values in that range
- If you used [x,null], then it would return all index values from 'x' onward.
- If you used [-x:null], then it would return all values from the end of the list, per the number given.

Looping through a Slice, 
```python
    words = ['murray', 'john', 'paul', 'ringo', 'george']
    for word in words[:3]:
        print(word.title())    
 ```
 - As it is [:3]... will STOP the list after the FIRST 3 values
 - if it were [:-3]... would STOP the list 3 indexes from the END
 - if it were [3:]... it would START the list 3 values in from the START of the list
 - if it were [-3:]... it would START the list from 3 values FROM THE END of the list
 - [*index value at the START of list* : *index value for the STOP of list*] 
 
 An additional colon i.e. [::] would be Start/Stop/STEP. Steps are counted form one index to the next, not the index themselves.
 ```python
    words = ['murray', 'john', 'paul', 'ringo', 'george', 'alan', 'robert', 'diana']
    for word in words[::3]:
        print(word.title())    
 ```        
Immutable lists are called *Tuples*. This means that once defined, it cannot be changed. Tuples are defined with (BRACKETS & COMMAS!!!), but called with Sqr brackets [] like with a list using the desired indiex number. Tuples can be redefined later in code.
```python
    dimensions = (200, 50)
    print(dimensions[0])
    print(dimensions[1])

    print("\nOriginal Dimensions : ")
    for dimension in dimensions:
        print(dimension)

    dimensions = (400, 100)
    print("\nModified Dimensions : ")
    for dimension in dimensions:
        print(dimension)    
 ```
##
### IF Statements

In short,  if *conditional_test*:
                   *do something*
 ```python
     cars = ['audi', 'bmw', 'jeep', 'jaguar']

     for car in cars:
         if car == 'bmw':
             print (car.upper())
         else:
             print (car.title())
 ```
- If you include 'or' and 'and' as keywords you can concatenate variable names ()or/and().
#### IF Else (chain & blocks) Statements
 ```python
      age = 17
      if age >= 18:
          print("You are old enough to vote!")
          print("Have you registered to vote yet?")
      else:
          print("Sorry, you are to young to vote!")
          print("Be sure to register to vote when you turn 18!")
 ```
- elif = if/elif/else will break out at first true statement. For mutiple True requierments use multiple IF
```python
      age = 12
        if age < 4:
            print ("Your admisson cost is $0!")
        elif age < 18:
            print("Your admission cost is $5!")
        else:
            print("Your admission costs $10!")

        age = 65

        if age < 4:
            price = 0
        elif age < 18:
            price = 5
        elif age < 65:
            price = 10
        else:
            price = 5

        print ("Your admission is $" + str(price) + "!")
 ```
 
 #### Dictionaries - Key-Value pairs
 variablename = {'key': 'value',}
 
 ```python
    sky_0 = {'color': 'blue'}
    print(sky_0['color'])
    
    >>>blue
 ```
 You can start with an empty dictionary {}, and add dictionaryname['key'] = 'value'. Value can be modified by restating/redeclaring them. Also dictionaries can be appended in this manner.
  ```python
     alien_0 = {}
     alien_0['color'] = 'green'
     alien_0['points'] = 10
     print(alien_0)

     alien_0 = {'color' : 'blue', 'points' : 7}
     print(alien_0)

     alien_0['x_position'] = 0
     alien_0['y_position'] = 25
     print (alien_0)
     
  >>>{'color': 'green', 'points': 10}
  >>>{'color': 'blue', 'points': 7}
  >>>{'color': 'blue', 'points': 7, 'x_position': 0, 'y_position': 25} 
 ```
 - To remove a value use the del keyword like so: del DictName['key']
 - To iterate/loop through a dictionary, specify the: key, value and .items()
 - .keys can also be used on the DictName to loop through the keys, but this action is standard Dict Loop.
 - Also using .keys or .values, calling out a 'key' will allow specific actions in a loop, including if'key'not in etc.
 ```python
     favorite_languages = {
    'stephen':'python',
    'jenn':'php',
    'kevin':['c#', 'python', 'haskel'],
    'fred':'haskel',
    }

     print(favorite_languages['kevin'])

     for name, language in favorite_languages.items():
         if language == 'php':
             print('\nName : ' + name.title())
             print('\nLanguage : ' + language.upper())
         else:
             print('\nName : ' + name.title())
             print('\nLanguage : ' + language.title())
 ```
 - To omit duplicates during loops use a set as follows:
 ```python
     favorite_languages = {
    'stephen':'python',
    'jenn':'php',
    'kevin':'c#',
    'fred':'python',
    'alvin':'c#',
    'simon':'python',
    'theodore':'python',
    'fred':'haskel',
    }


     for language in set(favorite_languages.values()):
         print(language.title())
 #This line uses i in place of name
     for i in set(favorite_languages.keys()):
         print(i.title())
 ```
##
### User Input and WHILE Loops

- input() runs the 'prompt' and awaits user input, this can be stored in a variable. Prompts should be clear, and can be stacked. By default these are seen as strings and therefore numbers must be converted using int().
 ```python
   prompt = "If you tell us who you are, we can personalize the messages you see!"
   prompt +="\nWhat is your first name? "

   name = input(prompt)
   print("\nHello, " + name + "!")

   age = input('\nHow old are you? ')
   age = int(age)
   half_age = age / 2.0
   print('\nHalf your life ago you were ' + str(half_age) + ' years old!')      
 ```
 - The while loop runs as long as a condition is true. It will loop until the condition is untrue (!=), a flag (read t/f god condition) or break are used.
 ```python
    #quit value
    prompt = "Tell me something and I will repeat it back to you: "
    prompt +="\nEnter 'quit' to end the program. "

    message = ""
    while message != 'quit':
        message = input(prompt)
        if message != 'quit':
            print(message)

    #flag value
    prompt = "Again, tell me something and I will repeat it back to you: "
    prompt +="\nEnter 'quit' to end the program. "

    active = True
    while active:
        message = input(prompt)

        if message == 'quit':
            active = False
        else:
            print(message)

    #break value
    prompt = "Tell me the name of a citiy you'd like to visit: "
    prompt +="\nEnter 'quit' to end the program. "

    while True:
        city = input(prompt)

        if city == 'quit':
            break
        else:
            print("\nI'd love to go to " + city.title() + "!")
 ```
 - You can also use continue in a loop, but avoid infinite loops, constantly true.
  ```python
     current_number = 0
     while current_number < 10:
         current_number += 1
         if current_number % 2 == 0:
             continue

         print(current_number)

         x = 1
         while x = <= 5:
             print(x)
             # next line moves the calculation forward, so no infinite!
             x += 1
 ```
 ##
 #### WHILE Loops - Lists/Dictionaries
 - Do not manipulate lists whilst looping through them, use dicitionaries in this regard.
  ```python
    unconfirmed_users = ['jim', 'fred', 'angus']
   confirmed_users = []

   while unconfirmed_users:
       current_user = unconfirmed_users.pop()

       print("Verifiying user: " + current_user.title())
       confirmed_users.append(current_user)

   print("\nThe following users have been confirmed:")

   for confirmed_user in confirmed_users:
       print(confirmed_user.title())


   # To completely remove all instances of value

   pets = ['dog', 'fish', 'cat', 'rabbit', 'dog', 'goldfish', 'cat']
   print(pets)

   while 'cat' in pets:
       pets.remove('cat')

   print(pets)
 ``` 
- You can also fill a dictionary with user input. 
 ```python
    responses = {}
    polling_active = True

    while polling_active:
        name = input("\nWhat is your name? ")
        response = input("\nWhat mountain would you like to climb one day? ")

        responses[name] = response

        repeat = input("\nWould you like to let another person respond? (yes/no) ")
        if repeat == 'no':
            polling_active = False

    print("\n--- Poll Results ---")
    for name, response in responses.items():
        print(name + " would like to climb " + response + ".")
  ``` 
##
### FUNCTIONS
- Function structure is simplistic. A Definitiion. Docstring. Code. Call. You can also pass information to a function via an Argument (information passed *from* a function like 'Jesse') or a Parameter (variable 'username' as shown below) as a piece of infomration *needed to perform* the function.

 ```python
   def greet_world():
       """Display a simple greeting."""
       print("Hello World!")

   greet_world()

   def greet_user_new(username):
       """Display a simple greeting to a user."""
       print("Hello, " + username.title() + "!")

   greet_user_new('jesse')
 
 ```
 - Positional Arguments: In same order as function definition. 'def some_variable(var_1, var_2):' i.e. ORDER MATTERS!!!
 - Keyword Arguments: In any order but defined keyword and value.

 ```python
   def describe_pet(animal_type, pet_name):
      """Display info about a pet"""
      print("\nI have a " + animal_type + ".")
      print("My " + animal_type + "'s name is " + pet_name.title() + ".")

   describe_pet('hamster', 'harry') #positional
   describe_pet('dog','willy') #positional
   describe_pet(pet_name='harry', animal_type='hamster') #keyword
   describe_pet(animal_type='hamster', pet_name='harry') #keyword
 ```
- Default values for parameters can be used if defined in function call. 'def some_variable(var_1, var_2='spam'):'. Default valuse must be listed after all non-default values, otherwise you'll impact positional arguments.
- Optional values can be null in the definition, run an if loop to change the value.

 ```python
  def build_person(first_name, last_name, age=''):
    """Return a dictionary of information about a person"""
    person = {'first': first_name, 'last': last_name}
    if age:
        person['age'] = age
    return person

   musician = build_person('jimi', 'hendrix', age=27)
   print(musician)
 ```
 - Avoid infinite loops and use functions like:
 ```python
     def greet_world():
         """Display a simple greeting."""
         print("Hello World!")

     greet_world()

     def greet_user_new(username):
         """Display a simple greeting to a user."""
         print("Hello, " + username.title() + "!")

     greet_user_new('jesse')

     def get_formatted_name(first_name, last_name):
         """Return a full name, neatly formatted"""
         full_name = first_name + ' ' + last_name
         return full_name.title()

     while True:
         print("\nPlease tell me your name: ")
         print("\n(Enter 'q' at any time to quit)")

         f_name = input("First name: ")
         if f_name == 'q':
             break
         l_name = input("Last name: ")
         if l_name == 'q':
             break

         formatted_name = get_formatted_name(f_name, l_name)
         print("\nHello, " + formatted_name + "!")
 ```
 
##
## File Explanation
### *Slogan Randomizer*
This is a simple syntax, which when run through multiple instances, creates a randomized sentance on each iteration.

### *Dog Age Calculator*
Simple code to prompt and calculate the age of your dog in human years 
  
