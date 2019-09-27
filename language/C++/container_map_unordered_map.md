###map
In a `map`, the *key* values are generally used to sort and uniquely identify the elements, while the mapped values store the content associated to this *key*. 
Internally, the elements in a `map` are **always sorted** by its key following a specific strict weak ordering criterion indicated by its internal comparison object (of type Compare).
`map` containers are generally slower than `unordered_map` containers to **access individual** elements by their key, but they **allow the direct iteration** on subsets based on their order.
Maps are typically implemented as *binary search trees*.
####Constructor
`empty`, range`(Iterator start, Iterator end)`, copy`map`, `initilaizer list`

####Iterators
`begin`, `end`, `rbegin`,`rend`,`cbegin`,`cend`, `crbegin`, `crend`

####Element access
`operator[]`: 
If `k` matches the key of an element in the container, the function returns a reference to its mapped value. If `k` does not match the key of any element in the container, the function inserts a new element with that key and returns a reference to its mapped value.

####Modifiers
`insert`: single element`mymap.insert(std::pair<char,int>('z', 500))`
`erase`: `(iterator position)`, `(key)`, range:`erase(iterator first, iterator last)`

####Operations
`find`: Searches the container for an element with a key equivalent to k and **returns an iterator** to **it** if found, otherwise it returns an iterator to `map::end`.
`lower_bound`: Returns an **iterator** pointing to the **first element** in the container whose key is **not considered to go before** k (i.e., either it is equivalent or goes after).
`upper_bound`: Returns an iterator pointing to the **first element** in the container whose key is **considered to go after** k.



###`std::unordered_map`
Unordered maps are associative containers that store elements formed by the combination of a *key* value and a *mapped value*, and which allows for fast retrieval of individual elements based on their keys.

Internally, the elements in the `unordered_map` are not sorted in any particular order with respect to either their key or mapped values, but organized into **buckets** depending on their **hash values** to allow for fast access to individual elements directly by their key values

`unordered_map` containers are faster than `map` containers to access individual elements by their `key`, although they are generally less efficient for range iteration through a subset of their elements.

####Constructor
`empty`, range`(iterator first, iterator last)`, `copy(map)`, `initializer list`
####Iterators
`begin`, `end`,`cbegin`, `cend`
####Element access
`operator[]`
####Element lookup
`find()`, ***no***`lower_bound()`, `upper_bound()`
####Modifiers
`insert`: single element`mymap.insert(std::pair<char,int>('z', 500))`
`erase`: `(iterator position)`, `(key)`, range:`erase(iterator first, iterator last)`