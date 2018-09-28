# Regular expressions

One of the most important aspects of programming for linguists is pattern matching. You will very often have to assess whether some string
matches some pattern, contains some sequence of characters, some number of characters, etc.

We’ve already seen that we can do this with what we’ve already learned. For example,
if we wanted to know if some string `s` contained the sequence 'ab', we could
simply write ’ab’ in `s` which would return `True` or `False`. If, on the other
hand, we wanted to know if a string contained ’a’ and then ’b’ with material
potentially intervening, we would have to do more. We might write a function like
this:

```python
import sys
#a and then b
def mymatch(s):
  i = 0
  #a flag to keep track of
  #whether we see an ’a’
  aFlag = False
  while i < len(s):
    if s[i] == ’a’:
      aFlag = True
      break
    i += 1
  #start looking for ’b’
  #where we left off
  while i < len(s):
    if s[i] == ’b’:
      #if we find ’b’, return
      #True of False depending
      #on whether we previously
      #saw ’a’
      return aFlag
    i += 1
  #if all that fails, return False
  return False

print(mymatch('Alice in ab Barcelona'))
```
The function `mymatch()` can be invoked with a command-line argument, so we
can test out how it applies to different strings. The logic of the function is that
we search the string for the first instance of ’a’ by iterating across the string with
the counter i. If we find it, we set the value of aFlag to True and exit the first
while loop. Then, without resetting i, we initiate another while loop to look
for ’b’. Not resetting the value of i means that the second loop picks up where
the first ended. Hence, the ’b’ must follow the (first) ’a’.
This is fine as it goes, but it doesn’t generalize. There are an infinite number of
patterns we might want to search for and writing a potentially complex matching
function for each one is at best tedious and at worst can lead to programming
errors.
