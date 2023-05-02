Download Link: https://assignmentchef.com/product/solved-comp1020-assignment4-doubly-linked-lists-recursion-and-sorting
<br>
In the recorded lectures, we saw how to implement regular linked lists. These are also called “singly” linked lists, because each node only has one link to the next node. There exist other types of linked lists. One of them is the “doubly” linked list, in which nodes contain two pointers instead of just one: a link to the previous node, and a link to the next node. The class that represents the doubly linked list usually stores two pointers to both ends of the list: references to the first and last nodes. Please see the figure below for an example of a doubly linked list:

In this assignment, you will have to implement methods in a doubly linked list. The main advantage of a doubly linked list is that you are allowed to go in both directions (backward and forward) from any node. Just like we have seen in the recorded lectures, the most important thing in any linked list is to think about all the special cases (empty list, list with only one node, etc.) and to update the links correctly after each operation. The only difference here is that you have twice the number of links to update compared to a singly linked list. If you forget to update some links, your list will be broken. You will be able to observe this when you print the list in both directions: if the list doesn’t contain the same nodes in both directions, it means that the list was not modified properly.

To make things more interesting, <u>we are not allowing you to use loops in this entire assignment (no exception)</u>. Everything must be done with <strong>recursion</strong> instead. By the end of this assignment, you will become masters at recursion!

<strong>Two template files</strong> (<strong>DoublyLinkedList.java</strong> and <strong>Node.java</strong>) are provided to you. They contain the instance variables that you need, accessor/mutator methods for them and one constructor in the Node class. You are <u>not allowed</u> to add any additional instance or class variables in the provided files, nor to modify the lines of code that are already provided. You <strong>must only add the requested methods</strong>, as described below (there shouldn’t be a need for any additional methods).

Note that the data that we store in the Node class is of type <strong>Number</strong>. The Number class is provided by Java (you can see the documentation here: <a href="https://docs.oracle.com/javase/8/docs/api/java/lang/Number.html">https://docs.oracle.com/javase/8/docs/api/java/lang/Number.html</a><a href="https://docs.oracle.com/javase/8/docs/api/java/lang/Number.html">)</a>. It is an abstract class, which serves as a superclass to all the objects representing numbers. In this assignment, we will only store these possible subclasses as possible data types in our Nodes: <strong>Integer</strong>, <strong>Long</strong> and <strong>Double</strong>.

Unless specified otherwise, all interface methods should be <strong>public</strong>. Helper methods (not supposed to be used by outside code) should normally be <strong>private</strong>. Since this assignment will be using a lot of recursion, and since recursive methods often need extra parameters, we will often implement a <strong>public</strong> interface method, which is meant to be used by outside code, and its role will be to call the <strong>private</strong> recursive version of the method with appropriate parameters. In most cases, you will have to find which parameters to use to make the recursion work in those private recursive versions of the methods (since they are private anyway, we will not test them directly in the automated tests, so you can define any parameter(s) that you need). Note that the public interface methods can also do some checks or deal with some easy cases, if you find it useful or appropriate.

Remember as usual to keep all of your methods short and simple. Make sure to call methods already created when appropriate, instead of duplicating code for no reason. There are no methods in this entire assignment that should require more than about <strong>20</strong> lines of code, not counting comments, blank lines, or {} lines (and many of them need much less than that). Also, unless specified otherwise, there should be <strong><em>no </em>println</strong> statements in your methods. Objects usually do not print anything, they only return <strong>String</strong> values from methods.

<strong>Testing Your Coding </strong>

We have provided sample test files for each phase to help you see if your code is working according to the assignment specifications.  As usual, these files are <em><u>starting</u></em><u> <em>points</em></u> for testing your code. Part of developing your skills as a programmer is to think through additional important test cases and to write your own code to test these cases. <em><u>For</u> <u>marking, we will use longer and more comprehensive tests</u></em>.

<strong>Phase 1: </strong>

First, implement these methods in the DoublyLinkedList class:




<ul>

 <li>A <strong>public void</strong> <strong>addFront(Number) </strong>method that adds a new Node containing the Number received as a parameter to the beginning (front) of the list. This method does not require recursion.</li>

 <li>A <strong>public void</strong> <strong>addEnd(Number) </strong>method that adds a new Node containing the Number received as a parameter to the end of the list. This method does not require recursion.</li>

 <li>A <strong>public int</strong> <strong>size() </strong> This method is the public interface to the <strong>sizeRec </strong>method described below. This method must return the size of the list (i.e. how many nodes are in the list).</li>

 <li>A <strong>private int sizeRec([parameter(s) of your choice])</strong> This method will use recursive calls (to itself) to move through the list and count the number of nodes. Choose parameter(s) that will allow you to do that.</li>

 <li>A <strong>public String toString()</strong> This method is the public interface to the <strong>toStringRec </strong>method described below. This method must return a String representation of the list, enclosed within the &lt;&lt; and &gt;&gt; pairs of characters (as in the example output shown below).</li>

 <li>A <strong>private String toStringRec([parameter(s) of your choice])</strong> This method will use recursive calls (to itself) to move through the list and build a String representation of it. Choose parameter(s) that will allow you to do that.</li>

 <li>A <strong>public String toStringReversed()</strong> This method is the public interface to the <strong>toStringReversedRec </strong>method described below. The goal of this method is to return a String representation of the list (also using the &lt;&lt; and &gt;&gt; pairs of characters), but in reverse order (i.e. starting from the end of the list).</li>

 <li>A <strong>private String toStringReversedRec([parameter(s) of your choice]) </strong> This method will use recursive calls (to itself) to move through the list (in the reverse order) and build a String representation of it. Choose parameter(s) that will allow you to do that.</li>

</ul>

You can test your classes using the supplied test program <strong>TestPhase1.java</strong>. You should get the output shown below.

<strong>&lt;&lt; 111 &gt;&gt; </strong>

<strong>&lt;&lt; 111 222.2 &gt;&gt; </strong>

<strong>&lt;&lt; 111 222.2 3000000000 &gt;&gt; </strong>

<strong>&lt;&lt; 0.777 111 222.2 3000000000 &gt;&gt; </strong>

<strong>&lt;&lt; 3000000000 222.2 111 0.777 &gt;&gt; The list has a size of: 4 </strong>

<strong>Phase 2:  </strong>

Next, implement these methods in the <strong>DoublyLinkedList</strong> class:




<ul>

 <li>A <strong>public static DoublyLinkedList createList(String)</strong> The ultimate goal of this method is to create and return a new DoublyLinkedList based on the parsing of a file (the filename is the received String parameter).</li>

</ul>

This method must open the file represented by the filename parameter <u>using a Scanner</u> (this is important for the next steps). Then, it must call the recursive method <strong>parseScanner</strong> described below. Your method must handle the type of exception thrown by doing this here, with an appropriate try-catch (<u>do not</u> add a “throws” statement to the signature of this method, otherwise the automated tests will fail).

Fun fact: This kind of method is often called a “factory method”. It is a design pattern that is used a lot in programming, or in other words, a general solution that is used often to solve a common problem (we’re not going to get into the details of design patterns here; you will see them in 2<sup>nd</sup> and 3<sup>rd</sup> year courses). This is completely out of the scope of this course, but if you are interested, you can read more about this here: <a href="https://www.geeksforgeeks.org/design-patterns-set-1-introduction/">https://www.geeksforgeeks.org/design</a><a href="https://www.geeksforgeeks.org/design-patterns-set-1-introduction/">–</a><a href="https://www.geeksforgeeks.org/design-patterns-set-1-introduction/">patterns</a><a href="https://www.geeksforgeeks.org/design-patterns-set-1-introduction/">–</a><a href="https://www.geeksforgeeks.org/design-patterns-set-1-introduction/">set</a><a href="https://www.geeksforgeeks.org/design-patterns-set-1-introduction/">–</a><a href="https://www.geeksforgeeks.org/design-patterns-set-1-introduction/">1</a><a href="https://www.geeksforgeeks.org/design-patterns-set-1-introduction/">–</a><a href="https://www.geeksforgeeks.org/design-patterns-set-1-introduction/">introduction/</a> <a href="https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/">https://www.geeksforgeeks.org/design</a><a href="https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/">–</a><a href="https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/">patterns</a><a href="https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/">–</a><a href="https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/">set</a><a href="https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/">–</a><a href="https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/">2</a><a href="https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/">–</a><a href="https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/">factory</a><a href="https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/">–</a><a href="https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/">method/</a>

<ul>

 <li>A <strong>private static void parseScanner(Scanner, DoublyLinkedList) </strong> This method will use recursive calls (to itself) to move through the Scanner received as a parameter and add to the list received as a parameter. This method must add to the list only the tokens read from the file (through the Scanner) that correspond to either an Integer, a Long or a Double. All other tokens must simply be ignored. In the end, the list must be in the same order as in the file.</li>

</ul>

You can test your class with <strong>TestPhase2.java </strong>and the text file <strong>list.txt</strong>.  You should get the output shown below.

<strong>&lt;&lt; 1 2 3 4 5 6.567 7000 8000 9000000 10000000000 11111111111 12.12 &gt;&gt; </strong>

<strong>&lt;&lt; 12.12 11111111111 10000000000 9000000 8000 7000 6.567 5 4 3 2 1 &gt;&gt; The list has a size of: 12 </strong>




<strong>Phase 3: </strong><strong> </strong>

Next, implement these methods in the <strong>DoublyLinkedList</strong> class:

<ul>

 <li>A <strong>private void removeNode(Node) </strong> This method does not use recursion. The goal of this method is to remove from the current list the Node that is received as a parameter (you can assume that the Node is for sure in this list). This method will be useful for other methods in this assignment, including the methods below.</li>

 <li>A <strong>public Node remove(int)</strong> This method is the public interface to the <strong>removeRec </strong>method described below. The goal of this method is to remove the Node that is at the index (i.e. position) received as a parameter (note that index 0 corresponds to the first Node). <u>It must also return the Node that was just removed</u>. If there is no Node at that index, or if the index received is a negative number, an IndexOutOfBoundsException must be thrown (you can do that here and/or in the recursive method below).</li>

 <li>A <strong>private Node removeRec([parameter(s) of your choice]) </strong> This method will use recursive calls (to itself) to move through the list and remove the correct Node (and return it). Choose parameter(s) that will allow you to do that.</li>

</ul>




You can test your class with TestPhase3.java.  You should get the output shown below:

<strong>&lt;&lt; 1 2 3 4 5 6.567 7000 8000 9000000 10000000000 11111111111 12.12 &gt;&gt; </strong>

<strong>The list has a size of: 12 </strong>

<strong>The removed Node contained: 3 The list has a size of: 11 </strong>

<strong>The removed Node contained: 4 The list has a size of: 10 </strong>

<strong>The removed Node contained: 5 </strong>

<strong>The list has a size of: 9 </strong>

<strong>The removed Node contained: 6.567 </strong>

<strong>The list has a size of: 8 </strong>

<strong>The removed Node contained: 7000 The list has a size of: 7 </strong>

<strong>The removed Node contained: 8000 </strong>

<strong>The list has a size of: 6 </strong>

<strong>The removed Node contained: 9000000 </strong>

<strong>The list has a size of: 5 </strong>

<strong>The removed Node contained: 10000000000 </strong>

<strong>The list has a size of: 4 </strong>

<strong>List (forward): &lt;&lt; 1 2 11111111111 12.12 &gt;&gt; List (backward): &lt;&lt; 12.12 11111111111 2 1 &gt;&gt; Seems like we have an invalid index! </strong>

<strong> </strong><strong>Phase 4: </strong><strong> </strong>

In this phase, we will add one method in the <strong>Node</strong> class, and two methods in the <strong>DoublyLinkedList</strong> class.




In the <strong>Node</strong> class, implement:

<ul>

 <li>A <strong>public int</strong> <strong>compareTo(Node)</strong> method that will compare this Node with the Node received as a parameter. As usual, the compareTo method must return an int value that is either a negative int, a positive int or 0, depending on whether this Node is smaller, greater or equal (respectively) to the Node received as a parameter.</li>

</ul>




We will use the ‘data’ instance variable to compare Nodes. Note that the type of the ‘data’ instance variable is Number, and the Number class does not define a compareTo method. You will have to follow these rules to compare the different possible subtypes of Numbers that can be stored in ‘data’:

<ul>

 <li>When comparing Nodes that contain different subtypes, we will always follow this ordering of subtypes: <strong>Integer &lt; Long &lt; Double</strong>. So for example, a Node containing an Integer will always be smaller than a Node containing a Long, no matter what the actual values are (e.g. 2 &lt; 1L in our system).</li>

 <li>When comparing Nodes that contain the same subtype of Number, an actual comparison of the values must be made to determine the order.</li>

</ul>




In the <strong>DoublyLinkedList</strong> class, implement:

<ul>

 <li>A <strong>public Node findMax() </strong> This method is the public interface to the <strong>findMaxRec </strong>method described below. The goal of this method is to return the largest Node in the list, using the compareTo method of the Node class. If the list is empty, it should simply return null.</li>

 <li>A <strong>private Node findMaxRec([parameter(s) of your choice]) </strong> This method will use recursive calls (to itself) to move through the list and return the largest Node in the list (using the compareTo method of the Node class). Choose parameter(s) that will allow you to do that.</li>

</ul>




You can test your class with TestPhase4.java.  You should get the output shown below:

<strong>&lt;&lt; 1 2 3 4 5 6.567 7000 8000 9000000 10000000000 11111111111 12.12 &gt;&gt; </strong>

<strong>The Node with the max value contains: 12.12 true </strong>

<strong>&lt;&lt; 3 4 5 6.567 7000 8000 9000000 10000000000 11111111111 12.12 &gt;&gt; false </strong>

<strong>&lt;&lt; 3 4 5 8000 9000000 10000000000 11111111111 12.12 &gt;&gt; true </strong>

<strong>&lt;&lt; 3 4 5 8000 9000000 10000000000 &gt;&gt; </strong>

<strong>The Node with the max value contains: 10000000000 </strong>

<strong>&lt;&lt; 9.99 3 4 5 8000 9000000 10000000000 &gt;&gt; </strong>

<strong>The Node with the max value contains: 9.99 </strong>

<strong>Phase 5: </strong><strong> </strong>

Finally, implement these methods in the <strong>DoublyLinkedList</strong> class:




<ul>

 <li>A <strong>public void orderedInsertRec(Node toInsert, Node current) </strong> This method is recursive, but we will not create an interface for this one. We will keep this method public here, because we want to be able to test it independently. For that reason, we also provide the required parameters: one Node that must be inserted, and the current Node, representing where to start the ordered insertion process.</li>

</ul>




The goal of this method is to make an ordered insertion of the toInsert Node, following the rules of the compareTo method defined in the Node class, following an ascending order from left to right. A call to this method would only affect the portion of the list starting from the first Node (of the list) to the current Node (the parameter). In other words, this recursive method is moving through the list backwards starting from the given current Node, and inserts the toInsert Node as soon as it finds the right spot for it.




This method is defined this way because it will be useful for the next two methods described below.




<ul>

 <li>A <strong>public void insertionSort() </strong> This method is the public interface to the <strong>insertionSortRec </strong>method described below. The goal of this method is to implement a recursive insertion sort algorithm, which will result in the full list being sorted in ascending order.</li>

 <li>A <strong>private void insertionSortRec([parameter(s) of your choice]) </strong> This method will use recursive calls (to itself) to move through the list, take the current Node and insert it in the right spot inside the sorted part of the list (it will be on the left), following the traditional insertion sort algorithm. Of course you should make use of the orderedInsertRec method here, and maybe other method(s) defined previously in this assignment. This method should be quite short. If you have more than 6-8 lines of code here, rethink your approach.</li>

</ul>




You can test your class with TestPhase5.java (make sure list.txt and list2.txt are in the same folder).  You should get the output shown below:

<strong>&lt;&lt; 22.1 &gt;&gt; </strong>

<strong>&lt;&lt; 5.55 22.1 &gt;&gt; </strong>

<strong>&lt;&lt; 1 5.55 22.1 &gt;&gt; </strong>

<strong>&lt;&lt; 1 111121212121212 5.55 22.1 &gt;&gt; </strong>

<strong>&lt;&lt; 1 600 111121212121212 5.55 22.1 &gt;&gt; </strong>

<strong>&lt;&lt; 1 600 111121212121212 0.5 5.55 22.1 &gt;&gt; </strong>

<strong>&lt;&lt; 1 600 111121212121212 0.5 5.55 22.1 77.789 &gt;&gt; </strong>

<strong> </strong>

<strong>Before sorting: </strong>

<strong>&lt;&lt; 1 2 3 4 5 6.567 7000 8000 9000000 10000000000 11111111111 12.12 &gt;&gt; </strong>

<strong>After sorting: </strong>

<strong>&lt;&lt; 1 2 3 4 5 7000 8000 9000000 10000000000 11111111111 6.567 12.12 &gt;&gt;  </strong>

<strong>Before sorting: </strong>

<strong>&lt;&lt; 10.1 1.5 0.25 4.75 11111111111111111 99999999999999999 55555555555555555 8 9 1 2 5 &gt;&gt; </strong>

<strong>After sorting: </strong>

<strong>&lt;&lt; 1 2 5 8 9 11111111111111111 55555555555555555 99999999999999999 0.25 1.5 4.75 10.1 &gt;&gt; </strong>

<strong> </strong>