# partition-list
class Solution {
public:




    ListNode* partition(ListNode* head, int x) {
        ListNode* smallerH = NULL, *smallerL = NULL;
        ListNode *greaterL = NULL, *greaterH = NULL;
        
        while(head!=NULL){ 
            if(head->val >= x){
                 
                if(greaterH == NULL){
                    greaterH=greaterL=head;
                }
                else{
                    greaterL->next = head; 
                    greaterL =greaterL->next;
                }              
             }
            
            else {
               
                if(smallerH == NULL){
                    smallerH=smallerL=head;
                }
                else{
                    smallerL->next = head; 
                    smallerL = smallerL->next;
                }
            }
            head=head->next;
        }
              
            if (greaterL != NULL) {
                greaterL->next = NULL; 
            }

            if (smallerH == NULL) { 
                 return greaterH; 
            } 
           
                
                smallerL->next = greaterH; 
                return  smallerH;    
    }
};
