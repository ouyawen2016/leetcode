```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        if(l2==null)
            return l1;
        if(l1==null)
            return l2;
        ListNode root = new ListNode(0);//新链的空头
        ListNode p = root;//标记一下头部
        while(l1!=null&&l2!=null){
            if(l1.val<l2.val){
                root.next=l1;
                l1 = l1.next;
            }else{
                root.next=l2;
                l2= l2.next;
            }
            root = root.next;
            
        }
        root.next=(l1==null?l2:l1);
        return p.next;
    }
}
```

