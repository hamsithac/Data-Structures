# Data-Structures


Merge two sorted linked lists and return it as a new sorted list. The new list should be made by splicing together the nodes of the first two lists.

Example:

Input: 1->2->4, 1->3->4
Output: 1->1->2->3->4->4

SOLUTION:

/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
 
 
 
class Solution {
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        if(l1==null){
            return l2;
        }
        
        if(l2==null){
            return l1;
        }
        
        if(l1.val<l2.val){
            ListNode small=mergeTwoLists(l1.next,l2);
            l1.next=small;
            return l1;
        }else{
             ListNode big=mergeTwoLists(l1,l2.next);
            l2.next=big;
            return l2;
        }
    }
}
