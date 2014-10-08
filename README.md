04_Linked_List_Lab
==================

Implement a simple linked list using pointers and classes.

Requirements
------------

1. Add, remove, get, and set should be O(1) if `i == 0` or if `i == size()-1`
2. Add, remove, get, and set should throw a string exception if `i >= size()`. Find should throw a string exception if `i > size()`
3. Do not leak memory (make sure remove and the destructor do the right thing)
4. `size()` is O(1) time (keep track of the numItems when you add or remove, so you can just return the variable)

Reading
=======
"Open Data Structures," Chapter 3, up through section 2 (DLList), http://opendatastructures.org/ods-cpp/3_Linked_Lists.html

Questions
=========

#### 1. Which of the above requirements work, and which do not? For each requirement, write a brief response.

1. find() does not search from the back of the list, so methods that use find() might not operate in O(1) on edge cases. Unverified.
2. All exceptions were caught as the testExceptions() method desired, so that it printed "SUCCESS: exception of type --- was caught".
3. Each time 'new' was called, a corresponding 'delete' call was made later, so there ought to be no memory leaks.
4. Done. Whenever a Node was added or removed, use numItems to keep a running tally. Then just use that in size().

#### 2. If we did an ArrayList instead of a LinkedList, which of the public methods would be faster, and which would be slower? Explain your answer.
			The get() and set() methods would be faster because ArrayList allows random access to the information, rather than the sequential access of LinkedList.
			The add() and remove() methods are slower in ArrayList because it needs to make a new array and copy everything over, 
					while a LinkedList just needs to change where four variables point, a trivial task.
#### 3. What is one question that confused you about this excercise, or one piece of advice you would share with students next semester?
			I confused myself for a bit while coding by not updating my numItems variable, which caused a lot of frustration before I found it.