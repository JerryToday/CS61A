# Object-Oriented Programming

```python
def amplify(f, x):
    """Yield the longest sequence x, f(x), f(f(x)), ... that are all true values
    
    >>> list(amplify(lambda s: s[1:], 'boxes'))
    ['boxes', 'oxes', 'xes', 'es', 's']
    >>> list(amplify(lambda x: x//2-1, 14))
    [14, 6, 2]
    """
    "*** YOUR CODE HERE ***"
    value = x
    while value:
        yield value
        value = f(value)

```

```python
class Person:
    """Person class.

    >>> steven = Person("Steven")
    >>> steven.repeat()       # initialized person has the below starting repeat phrase!
    'I squirreled it away before it could catch on fire.'
    >>> steven.say("Hello")
    'Hello'
    >>> steven.repeat()
    'Hello'
    >>> steven.greet()
    'Hello, my name is Steven'
    >>> steven.repeat()
    'Hello, my name is Steven'
    >>> steven.ask("preserve abstraction barriers")
    'Would you please preserve abstraction barriers'
    >>> steven.repeat()
    'Would you please preserve abstraction barriers'
    """

    def __init__(self, name):
        self.name = name
        "*** YOUR CODE HERE ***"
        self.lastSay = 'I squirreled it away before it could catch on fire.'

    def say(self, stuff):
        "*** YOUR CODE HERE ***"
        self.lastSay = stuff
        return stuff

    def ask(self, stuff):
        return self.say("Would you please " + stuff)

    def greet(self):
        return self.say("Hello, my name is " + self.name)

    def repeat(self):
        "*** YOUR CODE HERE ***"
        return self.lastSay
```

```python
class SmartFridge:
    """"
    >>> fridgey = SmartFridge()
    >>> fridgey.add_item('Mayo', 1)
    'I now have 1 Mayo'
    >>> fridgey.add_item('Mayo', 2)
    'I now have 3 Mayo'
    >>> fridgey.use_item('Mayo', 2.5)
    'I have 0.5 Mayo left'
    >>> fridgey.use_item('Mayo', 0.5)
    'Oh no, we need more Mayo!'
    >>> fridgey.add_item('Eggs', 12)
    'I now have 12 Eggs'
    >>> fridgey.use_item('Eggs', 15)
    'Oh no, we need more Eggs!'
    >>> fridgey.add_item('Eggs', 1)
    'I now have 1 Eggs'
    """
    def __init__(self):
        self.items = {}
    def add_item(self, item, quantity):
        if item in self.items:
            self.items[item] += quantity
        else:
            self.items[item] = quantity
        return f'I now have {self.items[item]} {item}'
    def use_item(self, item, quantity):
        self.items[item] -= min(quantity, self.items[item])
        if self.items[item] == 0:
            return f'Oh no, we need more {item}!'
        return f'I have {self.items[item]} {item} left'
```
