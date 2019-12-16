# Python Cheatsheet
**The small flashy stuff I may never use, but would be cool to keep track of.**


## Contents
- [Saving and Reading/Loading Lists](#lists-as-files)

___
## Lists as Files
### Using pickle
Use `pickle`'s **dump** and **load** features to write and load lists.
```python
import pickle

some_list = ['This', 'is', 'really','pretty', 'cool']
# Write the list to a file in binary form
with open('some_file.txt', 'wb') as f:
  pickle.dump(some_list, f)

# Read the data from the newly created file as a list
with open('some_file.txt', 'rb') as f:
  loaded_list = pickle.dump(f)
```
The only "problem" (atleast I havent tested it out yet - probably try 'ab') is one cannot simply append to the file, it has to be overwritten everytime.

### Importing from a py file
So, this here is the main reqason I even started this cheatsheet; I got this off a stackoverflow question, but forgot to bookmark it :sweat_smile: . The concept here is that one can literally write the required list to a py file and then load it like a library to access the list.
```python
some_list = ['This', 'is', 'really','pretty', 'cool']

# Write the list to file
with open('some_file.py', 'w') as f:
  f.write('some_list = %s' % some_list)

# Load the list using import
from some_file import some_list as loaded_list
print(loaded_list)
```
Quite flashy and not a reccommended approach
