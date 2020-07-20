## :zap: Question

> Remove all elements from a linked list of integers that have value val.
> Example:
> Input:  1->2->6->3->4->5->6, val = 6
> Output: 1->2->3->4->5

## :peach: Solution
```
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
    public ListNode removeElements(ListNode head, int val) {
       ListNode dummy = new ListNode();
        dummy.next = head;
        ListNode pre = dummy;
        ListNode cur = head;
        while(cur != null) {
            if(cur.val == val) {
                pre.next = cur.next;
                cur = cur.next;
            }  else {
                pre = cur;
                cur = cur.next;
            }
        }
        
        return dummy.next;
    }
}
```
