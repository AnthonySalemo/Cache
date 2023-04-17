# Cache
Creating a cache of tweet information using some relevance to decide how the cache is populated and updated.
The Cache is structured as a class with many built in functions.

The initial structure of the Cache is a dictinary and a limit value.

Within the class are currently 5 functions:
1. current_cache_size(self)
  This function just returns the total amount of objects added to the dictionary
  
2. add_update(self, key, value)
  This function currently uses a separate primary key to add a value(json object) into the dictionary.
  If the cache reaches the limit value specified it will call the remove_least_relevant() function.
  Note: In later iterations it will be able to read the primary key from the value
  
3. remove_least_relevant(self)
  This function currently looks through the entire cache and removes the json object with the lowest relevance term.
  Note: The relevance term will be some term related to popularity/tweet relevance.

4. initial_population(self, database)
  This function currently takes the most and least relevant term and adds them to the cache.
  Note: In later iterations it will initially take the 10 least relevant terms and then the most relevant terms 
  until it fills up. This will be able to test and see if both the add_update() function works as well as the 
  remove_least_relevant() function.
  
5. up_to_date(self)
  This function removes tweets that are older than a week from their initial post. 
  Note: in later iterations it will run on its own every 24 hours.
