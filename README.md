# Cache
Creating a cache of tweet information using some relevance to decide how the cache is populated and updated.
The Cache is structured as a class with many built in functions.

The initial structure of the Cache is a dictinary, a minheap list, and a limit value.

Within the class are currently 6 functions:
1. current_cache_size(self)
  This function just returns the total amount of objects added to the dictionary

2. initial_population(self, database)
  This function finds every individual tweet within the mongoDB database and attempts to add them to the cache

3. add_update(self, key, value)
  This function first checks that the current key is already in the cache, then if the cache limit is met and if so 
  it will check if the current key's relevance is greater than the least relevant item in the cache. If it is, call 
  function 4. Then add to cache and dictionary.
  
4. remove_least_relevant(self, least_relevant_key, least_relevant_value_in_cache)
  This function removes the least relevant items from both the cache and the minheap list then reorganizes the heap.

5. least_relevant_term(self)
  This function takes the first elements from the minheap and returns them
  
6. minheap_sort(self, key, value)
  This function adds to the minheap list with the relevance value being the key, and the key as the stored value.
