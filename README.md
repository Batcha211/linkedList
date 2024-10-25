import java.util.LinkedList;

public class Main {
    static class Node {
         int data;
         Node next;

         public Node (int data) {
             this.data = data;

         this.next = null;



         }


     }

     static class linkedList {
         Node head;

         public void InsertAtBeginning(int data) {
             Node newNode = new Node(data);
             newNode.next = head;
             head = newNode;
         }

         public void print() {
             Node temp = head;
             while (temp != null) {
                 System.out.print(temp.data + " ");
                 temp = temp.next;
             }
             System.out.println();
         }

         public void DeleteNode(int key) {
             Node temp = head;
             Node prev = null;
             if (temp !=  null && temp.data == key){
                 head = temp.next;
                 return;
             }
             while (temp != null && temp.data != key) {
                 prev = temp;
                 temp = temp.next;
             }
             if (temp == null) {
                 return;
             }
             prev.next = temp.next;
         }
         public void SearchNode(int key) {
             Node temp = head;
             while (temp != null && temp.data != key) {
                 temp = temp.next;
             }
             if (temp == null) {
                 System.out.println("Node" + key + " not found");
             } else {
                 System.out.println("Node" + key + " found");
             }
         }

     }



     public static void main(String[] args) {
         linkedList myList = new linkedList();

         myList.InsertAtBeginning(10);
         myList.InsertAtBeginning(20);
         myList.InsertAtBeginning(30);

         myList.print();
         myList.DeleteNode(20);
         myList.print();

         myList.SearchNode(15);
         myList.SearchNode(10);
     }
}
