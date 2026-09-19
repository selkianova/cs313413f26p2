TestList.java and TestIterator.java

TODO also try with a LinkedList - does it make any difference?

No, it does not make any behavioral difference. Both ArrayList and LinkedList implement the same `List` interface, so they share the exact same method signatures and operational contract.

TestList.java

testRemoveObject()

  list.remove(5); // what does this method do?

  	This calls `remove(int index)`. It removes the specific element located at index position 5 in the list.

  list.remove(Integer.valueOf(5)); // what does this one do?

  	This calls `remove(Object o)`. It searches the list and removes the very first occurrence of an object that has the integer value of 5, regardless of its index position.
TestIterator.java

testRemove()

  i.remove(); // what happens if you use list.remove(77)?

  	If you use `list.remove(77)` directly on the list while an iterator is currently active, Java throws a `ConcurrentModificationException`. You must use `i.remove()` to safely delete elements during an active iteration.
TestPerformance.java

State how many times the tests were executed for each SIZE (10, 100, 1000 and 10000) to get the running time in milliseconds and how the test running times were recorded.

SIZE 10
#1

testArrayListAddRemove:  val1
testLinkedListAddRemove: val1
testArrayListAccess:     val1
testLinkedListAccess:    val1

SIZE 100
#1

testArrayListAddRemove:  val1
testLinkedListAddRemove: val1
testArrayListAccess:     val1
testLinkedListAccess:    val1

SIZE 1000
#1

testArrayListAddRemove:  val1
testLinkedListAddRemove: val1
testArrayListAccess:     val1
testLinkedListAccess:    val1

SIZE 10000
#1

testArrayListAddRemove:  val1
testLinkedListAddRemove: val1
testArrayListAccess:     val1
testLinkedListAccess:    val1

listAccess - which type of List is better to use, and why?

  ArrayList is significantly better for access operations. Because it is backed by an array, it provides constant-time O(1) memory access to any element via its index. LinkedList requires O(n) time since it must traverse the nodes one by one.
listAddRemove - which type of List is better to use, and why?

LinkedList is theoretically better for frequent Add/Remove operations, especially near the beginning or middle. It only needs to update node pointers in O(1) time. An ArrayList requires shifting all subsequent array elements, taking O(n) time.