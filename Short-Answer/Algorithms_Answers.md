Add your answers to the Algorithms exercises here.

## Exercise I

a) The runtime for this one would seem to be `O(n)` since we're checking a < n^3, while we're incrementing a by n^2 each time.

b) This one appears to be trickier, but it's simply `O(n^3)`. 
There are little bits shaved off in the first three loops (the O(n) loops), but they still can be estimated to O(n) rather than O(n-2) or something of the sort, and the last loop is constant time.

c) This one also looks a little tricky, but it'd be `O(n)`. It gets recursively called once each go around, and the answer should effectively be bunnies * 2 since 2 ears are added for each bunny.

## Exercise II

Suppose that you have an _n_-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor _f_ or higher, and doesn't get broken if dropped off a floor less than floor _f_. Devise a strategy to determine the value of _f_ such that the number of dropped eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode and give the runtime complexity of your solution.

This specifically seems to call for binary search, which would be a `O(log(n))` solution. We could also use simple search, `O(n)`, but both are relatively straight forward, so I'll go with the more efficient, logical solution.

Here's my python-esque psuedo-code, with some assumptions for input:
```
def find_first_unsafe_floor(n, eggs):
  visited = {}
  if n <= 0:
    raise ValueError('Buildings must have more than 0 floors!')

  found = False

  while len(eggs) > 0:
    egg = eggs.pop()
    egg.throw(mid) # throws off of mid'th floor
    if egg.is_broken:
      if mid in visited:
        return mid
      mid = mid//2
      visited[mid] = True
    else:
      mid += mid//2
```
I wanted to write out a nearly complete program so as to show some of the subtleties. The last thing needed for this to be complete would be some exact implementation of `egg`, and the throwing of it.

Again, the time complexity would be `O(log(n))`.
