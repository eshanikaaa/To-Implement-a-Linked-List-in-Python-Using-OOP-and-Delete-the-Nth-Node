class Node:
    """Represents a single node in the linked list."""
    def __init__(self, data):
        self.data = data
        self.next = None


class LinkedList:
    """Manages the linked list and provides operations."""
    def __init__(self):
        self.head = None

    def add_node(self, data):
        """Adds a node to the end of the linked list."""
        new_node = Node(data)
        if self.head is None:
            self.head = new_node
            return
        current = self.head
        while current.next:
            current = current.next
        current.next = new_node

    def print_list(self):
        """Prints all elements in the linked list."""
        current = self.head
        if not current:
            print("List is empty.")
            return
        while current:
            print(current.data, end=" -> ")
            current = current.next
        print("None")

    def delete_nth_node(self, n):
        """Deletes the nth node (1-based index) from the linked list."""
        try:
            if self.head is None:
                raise Exception("Cannot delete from an empty list.")

            if n <= 0:
                raise IndexError("Invalid index. Index must be 1 or greater.")

            if n == 1:
                print(f"Deleting node {n} with value {self.head.data}")
                self.head = self.head.next
                return

            current = self.head
            for _ in range(n - 2):
                if current.next is None:
                    raise IndexError("Index out of range.")
                current = current.next

            if current.next is None:
                raise IndexError("Index out of range.")

            print(f"Deleting node {n} with value {current.next.data}")
            current.next = current.next.next

        except Exception as e:
            print(f"Error: {e}")


#Sample Test Case
if __name__ == "__main__":
    ll = LinkedList()

    # Adding nodes
    ll.add_node(10)
    ll.add_node(20)
    ll.add_node(30)
    ll.add_node(40)
    ll.add_node(50)

    print("Original List:")
    ll.print_list()

    # Delete the 3rd node
    ll.delete_nth_node(3)
    print("\nAfter deleting 3rd node:")
    ll.print_list()

    # Delete the 1st node
    ll.delete_nth_node(1)
    print("\nAfter deleting 1st node:")
    ll.print_list()

    # Delete out-of-range node
    ll.delete_nth_node(10)

    # Delete from empty list
    empty_ll = LinkedList()
    empty_ll.delete_nth_node(1)
