# PartitionLinkedlist
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* partition(ListNode* head, int x) {
        if(head==nullptr || head->next==nullptr) return head;
        ListNode* tmp = new ListNode(-1);
        ListNode* tmp2 = tmp;
        ListNode* temp = head;
        while(temp){
            if(temp->val<x){
                tmp2->next = new ListNode(temp->val);
                tmp2 = tmp2->next;
            }
            temp = temp->next;
        }
        while(head){
            if(head->val>=x){
                tmp2->next = new ListNode(head->val);
                tmp2 = tmp2->next;
            }
            head = head->next;
        }
        return tmp->next;
    }
};
