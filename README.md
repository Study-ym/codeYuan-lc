# codeYuan-lc
# 刷题记录
## 链表
### 1.相交链表
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */
public class Solution {
    public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
        int m=getLength(headA),n=getLength(headB);
        ListNode a=headA,b=headB;
        if(m>n){
            for(int i=0;i<m-n;i++){
                a=a.next;
            }
            while(a!=b){
                a=a.next;
                b=b.next;
            }
        }else{
            for(int i=0;i<n-m;i++){
                b=b.next;
            }
            while(a!=b){
                a=a.next;
                b=b.next;
            }
        }
        return a;
    }
    public int getLength(ListNode node){
	if(node.next==null)return 0;
	int count=0;
	ListNode cur=node.next;
	while(cur!=null){
		cur=cur.next;
		count++;
	}
		return count;
    }
}
```
### 2.删除链表的倒数第N个节点
```
