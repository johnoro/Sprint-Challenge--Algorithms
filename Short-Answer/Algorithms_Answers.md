Add your answers to the Algorithms exercises here.

## Exercise I

a) The runtime for this one would seem to be `O(n)` since we're checking a < n^3, while we're incrementing a by n^2 each time.

b) This one appears to be trickier, but it's simply `O(n^3)`. 
There are little bits shaved off in the first three loops (the O(n) loops), but they still can be estimated to O(n) rather than O(n-2) or something of the sort, and the last loop is constant time.

c) This one also looks a little tricky, but it'd be `O(n)`. It gets recursively called once each go around, and the answer should effectively be bunnies * 2 since 2 ears are added for each bunny.

## Exercise II


