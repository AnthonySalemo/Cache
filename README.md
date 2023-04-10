# Cache
Creating a cache of tweet information using some relevance to decide how the cache is populated and updated.
The Cache is structured as a class with many built in functions.

The initial structure of the Cache is a dictinary and a limit value.

Within the class are currently 3 functions:
1. current_cache_size(self)
  This function just returns the total amount of objects added to the dictionary
  
2. add_update(self, key, value)
  This function currently uses a separate primary key to add a value(json object) into the dictionary.
  If the cache reaches the limit value specified it will call the remove_least_relavent() function.
  Note: In later iterations it will be able to read the primary key from the value
  
3. remove_least_relavent(self)
  This function currently looks through the entire cache and removes the json object with the lowest relevance term.
  Note: THe relavence term will be some term related to popularity/tweet relevance.
