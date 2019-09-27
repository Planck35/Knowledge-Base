###`std::forward_list`
Forward lists are sequence containers that allow **constant** time **insert** and **erase** operations anywhere within the sequence.
Forward lists are implemented as **singly-linked lists**; 
Singly linked lists can store each of the elements they contain in **different and unrelated storage locations**. 
The ordering is kept by the association to each element of a link to the next element in the sequence.

The main design difference between a `forward_list` container and a `list` container is that the first keeps internally **only a link to the next** element, while the latter keeps two **bidirect** links per element: one pointing to the next element and one to the preceding one, allowing efficient iteration in both directions, but consuming additional storage per element and with a **slight higher time** overhead inserting and removing elements. forward_list objects are thus more efficient than list objects, although they can only be iterated forwards.

The main drawback of `forward_lists` and `lists` compared to these other sequence containers is that they **lack direct access** to the elements by their position, which takes linear time in the distance to access arbitrary. They also consume some extra memory to keep the linking information associated to each element.

`Forward_list` is the only standard container to deliberately lack a `size` member function for efficiency considerations

####Constructor
`default` `fill(n,val)` `range: InputIterator first, InputIterator last`
 `copy`

#### Iterators
`before_begin()`: returns an iterator pointing to the position before first element. The iterator shall not be **dereferenced**.
`begin()`, `end()`, `cbefore_begin()`, `cbegin()`, `cend()`

###Element access(Only one)
`front`: Returns a **reference** to the **first element** in the forward_list container.

#### Modifiers
`push_front`: Insert element at beginning
`pop_front`: Delete first element
`insert_after`: `(iterator position, val)` or `(iterator position, n, val)`
`erase_after`: `(iterator position)` or `(iterator position, iterator last)` Removes from the `forward_list` container either a single element(the one after position) or a range of elements.
`remove`: Remove **all** elements with specific value
`remvoe_if`: Remove elements that **fulfill** condition (which return `true` on remove, `false` on don't remove)
`sort`: sorts the elements in the forward_list, altering their position within the container
`unique`: take no parameters, removes all but the first element **from every consecutive group of equal elements** in the container.
`merge`: Merges x into the forward_list by transferring all of its elements at their respective ordered positions into the container (both containers **require** **be ordered**).
`reverse`: Reverses the order of the elements in the forward_list container.


###`std::list`
Lists are sequence containers that allow constant time insert and erase operations anywhere within the sequence, and iteration in both directions. List containers are implemented as doubly-linked lists. 
The main drawback of `lists` and `forward_lists` compared to these other sequence containers is that they **lack direct access** to the elements by their position; For example, to access the sixth element in a list, one **has to iterate** from a known position (like the beginning or the end) to that position.
####Constructor
`default` `fill(n,val)` `range: InputIterator first, InputIterator last`
 `copy`
####Iterators
`begin()`, `end()`, `rbegin()`, `rend()`，`cbegin()`, `cend()`, `crbegin()`, `crend()`
####Element access
`front()` a reference to the first element
`back()` a reference to the last element
####Modifiers
`push_front`: Insert element at beginning
`pop_front`: Delete first element
`push_back`: Add element at the end
`pop_back`: Delete last element
`insert`: `(iterator position, value)` `(iterator position, size n, value)` `(iterator start, iterator end)` 
`erase`:single element:`(iteration pos)`, range: `(iterator start, iterator end)`
`remove`: Remove **all** elements with specific value
`remvoe_if`: Remove elements that **fulfill** condition (which return `true` on remove, `false` on don't remove)
`sort`: sorts the elements in the forward_list, altering their position within the container
`unique`: take no parameters, removes all but the first element **from every consecutive group of equal elements** in the container.
`merge`: Merges x into the forward_list by transferring all of its elements at their respective ordered positions into the container (both containers **require** **be ordered**).
`reverse`: Reverses the order of the elements in the forward_list container.