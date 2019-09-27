###`std::array` 
constructor example: `std::array<int,5> myarray = { 5, 19, 77, 34, 99 };`

Array class are fixed-size sequence containers, can not be expanded or contracted dynamically.

####Iterators
`begin`: Return iterator to beginning

`end`: Returns an iterator pointing to the **past-the-end** element in the array container
        The past-the-end element is the theoretical element that would follow the last element in the array. 
        It does not point to any element, and thus shall not be dereferenced.

`rbegin`: Returns a reverse iterator pointing to the **last** element in the array container. **Not** the one **past-the-end** 

`rend`: Returns a reverse iterator pointing to the theoretical element preceding the first element in the array (which is considered its reverse end).
####Capacity
`size`: Returns the number of elements in the `array` container
The size of an array object is always equal to the second template p**arameter used to instantiate** the array template class (N).
`empty`: Return a `bool` value indicating whether the array container is empty, i.e. whether its `size` is 0.
####Element acess
`operator[]`: Returns a **reference** to the element at position n in the array container.

`at`: functionality is the with `[]`, but it automatically checks whether n is within the bounds of valid elements in the container, throwing an out_of_range exception if it is not.

`front`: Returns a reference to the first element in the array container. 
        If the array object is const-qualified, the function returns a const_reference

`back`: Returns a reference to the last element in the array container.

####Modifiers
`fill`: Sets val as the value for all the elements in the array object.

###`std::deque`
In any case, `deque` allow for individual elements to be accessed directly through random access iterators. It have efficient insertion and deletion of elements at the beginning of the sequence and at its end. 
But unlike `vectors`, `deques` are not guaranteed to store all its elements in **contiguous** storage locations.
####Constructor
(1) empty container constructor (default constructor)
(2) fill constructor Constructs a container with n elements. Each element is a copy if val.
(3) range constructor: Constructs a container with as many elements as the range [first,last), with each element constructed from its corresponding element in that range, in the same order.
(4) copy constructor.
```C++
std::deque<int> first;                                // empty deque of ints
std::deque<int> second (4,100);                       // four ints with value 100
std::deque<int> third (second.begin(),second.end());  // iterating through second
std::deque<int> fourth (third); 
```
####operator=
Assigns new contents to the container, **replacing** its current contents, and modifying its size accordingly.
```C++
first = std::deque<int>();
```
####Iterators
The same.
####Capacity
Resizes the container so that it contains n elements.
If *n* is smaller than the current container size, the content is reduced to its first n elements, removing those beyond (and destroying them).
If *n* is greater than the current container size, the content is expanded by inserting at the end as many elements as needed to reach a size of *n*. If *val* is specified, the new elements are initialized as copies of *val*, otherwise, they are value-initialized. Otherwise, we will use default constructor. e.g. for `int`, it is zero

####Element access
The same

####Modifier
`push_back`: Add element at the end
`push_front`: Insert element at beginning
`pop_back`: Delete last element
`pop_front`: Delete first element
`insert`: `insert (const_iterator position, const value_type& val);` `single element`, `fill`, `range`