### EX: 11.e Doubly Linked List (Insertion in forward and reverse direction)


### Aim:
To Type a python function to insert element in the doubly linked list in forward and reverse direction.
### Algorithm:


#### 1. **Start**

#### 2. **Initialize Node Class**

* Define a class `Node` with:

  * `data`: stores the node's value
  * `next`: reference to the next node (initially `None`)
  * `prev`: reference to the previous node (initially `None`)

#### 3. **Initialize DoublyLinkedList Class**

* Define `DoublyLinkedList` class with:

  * `head`: pointer to the first node, initially `None`

#### 4. **Define `push(new_data)`**

* Create a new node with `new_data`
* Set its `next` to current `head`
* If the list is not empty:

  * Set current head’s `prev` to new node
* Set new node as the new `head` of the list

#### 5. **Define `append(new_data)`**

* Create a new node with `new_data`
* If the list is empty:

  * Set new node as `head` and return
* Else:

  * Traverse from `head` to the last node
  * Set last node’s `next` to new node
  * Set new node’s `prev` to last node

#### 6. **Insert Elements**

Call insert methods in this sequence:

* `append(1)` → List: 1
* `push(3)` → List: 3 <-> 1
* `push(5)` → List: 5 <-> 3 <-> 1
* `append(7)` → List: 5 <-> 3 <-> 1 <-> 7

---

#### 7. **Define `printList(node)`**

* **Forward Traversal**:

  * Start from `node` (head)
  * Print `data` while traversing using `next`
  * Track the last node
* **Reverse Traversal**:

  * From last node, print `data` while traversing using `prev`

#### 8. **Call `printList(llist.head)`**

* Outputs elements in forward and reverse order.

#### 9. **End**

Would you like a visual diagram of the final list structure?


### Program:
```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None
  
class DoublyLinkedList:
    def __init__(self):
        self.head = None
  
    def push(self, new_data):
        new_node = Node(new_data)
        new_node.next = self.head
        if self.head is not None:
            self.head.prev = new_node
        self.head = new_node
        
    def append(self, new_data):
        new_node = Node(new_data)
        if self.head is None:
           self.head = new_node
           return
        last = self.head
        while last.next:
            last = last.next
        last.next = new_node
        new_node.prev = last
        return
  
    def printList(self, node):
        print("\nTraversal in forward direction")
        while node:
            print(node.data)
            last = node
            node = node.next
        print("\nTraversal in reverse direction")
        while last:
            print(last.data)
            last = last.prev
 
llist = DoublyLinkedList()
  
llist.append(1)
llist.push(3)
llist.push(5)
llist.append(7)

llist.printList(llist.head)
```
### Output:
 
![image](https://github.com/gokulkrishnan2005/19CS301-Module11/blob/main/11%20seb.png)

 

### Result: Thus, the given program is implemented and executed successfully.

