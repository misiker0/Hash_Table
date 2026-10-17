# Hash Table

A simple hash table in Python, built with a `HashTable` class. Built as part of the freeCodeCamp Scientific Computing with Python certification.

## How it works

- `hash(string)` turns a string into an integer by adding up the character codes of its letters.
- Items are stored in a dictionary called `collection`, keyed by that hash value.
- Each hash value holds a nested dictionary of `key: value` pairs. When two keys produce the same hash (a collision), both are kept in the same nested dictionary.

## Methods

- `add(key, value)` stores a value, replacing it if the key already exists
- `lookup(key)` returns the value for a key, or `None` if the key isn't there
- `remove(key)` deletes a key and does nothing if it doesn't exist. If this empties a hash value's dictionary, that entry is removed too.
- `hash(string)` returns the hash value of a string

## Usage

```python
from Hash_Table import HashTable

ht = HashTable()
ht.add('golf', 'sport')
ht.add('fogl', 'anagram')       # same letters as 'golf', so the same hash

print(ht.hash('golf'))          # 424
print(ht.collection)            # {424: {'golf': 'sport', 'fogl': 'anagram'}}
print(ht.lookup('golf'))        # sport
print(ht.lookup('fogl'))        # anagram
print(ht.lookup('missing'))     # None

ht.remove('golf')
print(ht.lookup('golf'))        # None
print(ht.collection)            # {424: {'fogl': 'anagram'}}

ht.remove('fogl')
print(ht.collection)            # {}
```

## Running it

Requires Python 3. The file defines the class but doesn't print anything on its own. Import it from another script as shown above, or add test code at the bottom of the file.

## Limitations

This hash function is for learning. Any strings with the same letters collide (`'golf'` and `'fogl'`), so a real hash table would use a better function.

## What I practiced

- Classes and instance attributes
- Nested dictionaries
- Handling collisions
- Checking for missing keys before reading or deleting
