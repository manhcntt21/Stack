//Định nghĩa struct
#include<stdlib.h>
#include<stdio.h>
#include<windows.h>
struct node {
	int data;
	struct node* next;
};
typedef struct node* _ref;
_ref getNode(int x);
void addFirst(_ref *head, _ref *tail, int k);
void addMid(_ref *head, int position,int k);
void addTail(_ref *head, _ref *tail, int k);
void deleFirst(_ref *head);
void deleMid(_ref *head, int position,int k);
void deleTail(_ref *head, _ref *tail, int k);
// xoa giua
void deleMid(_ref *head, int position) {
	int tmp = 0;
	_ref p = *head;
	_ref q;
	while(p->next&&tmp<position) {
			tmp++;
			p = p -> next;
		}
	if(tmp>position&&position<0) {
		printf("Vi tri khong ton tai de chen");
		exit(0);
	}
	if(position==0) {
		printf("Hay chon ham chen dau");
		exit(0);
	}
	else {
		while(p->next&&tmp<position) {
			p = p -> next;
		}
		q = p->next;
		p->next = q->next;
		free(q);

	}
}
// xoa dau
void deleFirst(_ref *head) {
	_ref p;
	if(*head==NULL)
		free(*head);
	else {
		 p = *head;
		*head = (*head)->next;
		free(p);
	}
}
// xóa cuoi
void deleTail(_ref *head,_ref *tail) {
	_ref i;
	if(*head==NULL)
		free(*tail);
	else {
		while(i->next!=*tail) {
            i=i->next;
		}
		free(*tail);
		*tail = i;
		i->next = NULL;
	}
}
void detroyList(_ref head);

// Khởi tạo một node
_ref getNode(int x) {
	_ref p;
	p = (_ref)malloc(sizeof(_ref));
	if(!p) {
		printf("Cap phat khong thanh cong");
		exit(0);
	}
	else {
		p->data = x;
		p->next = NULL;
	}
	return p;
}
// thêm phần tử đầu vào danh sách
void addFirst(_ref* head, _ref* tail, int k) {
	_ref p =getNode(k);
	if(*head==NULL) {
		*head = *tail = p;
	}
	else {
		p->next = *head;
		*head = p;
	}
}
// them phần tử vào giữa danh sach( chen vao sau phan tu do)
void addMid(_ref *head, int position,int k) {
	int tmp = 0;
	_ref p = *head;
	_ref q =getNode(k);
	while(p->next&&tmp<position) {
			tmp++;
			p = p -> next;
		}
	if(tmp>position) {
		printf("Vi tri khong ton tai de chen");
		exit(0);
	}
	if(position==0) {
		printf("Hay chon ham chen dau");
		exit(0);
	}
	else {
		while(p->next&&tmp<position) {
			p = p -> next;
		}
		q->next = p->next;
		p->next = q;

	}
}
// thêm phần tử vào cuối
void addTail(_ref * head, _ref * tail, int k) {
	_ref p = getNode(k);
	if(*head==NULL)
		*head = *tail = p;
	else {
		(*tail)->next = p;
		*tail = p;
	}
}
//duyet danh sach
void printList(_ref head) {
	_ref p = head;
	while(p) {
		printf("   %d",p->data);
		p=p->next;
	}
}

// huy danh sach
void detroyList(_ref head) {
	_ref p ;
	while(head) {
		p = head;
		head = p -> next;
		free(p);
	}
}

int main() {
	_ref head = NULL, tail = NULL;
	int k;
	int position;
	char ch;
	while(1) {
                    system("cls");
		printf("\n_______________Menu___________________");
		printf("\nPut 1 to addFirst:   			 		");
		printf("\nPut 2 to addTail:   			 		");
		printf("\nPut 3 to addMid:   	                ");
		printf("\nPut 4 to deleFirst:   			 		");
		printf("\nPut 5 to deleTail:   			 		");
		printf("\nPut 6 to deleMid:   	                ");
		printf("\nPut 7 to printList:                   ");
		printf("\nPut 8 to detroyList and exit        \n");
		ch = getchar();
		switch(ch) {
			case '1': {
				system("cls");
				printf("\nPut 0 to Out 1");
				while(1) {
					printf("\naddFirst: phan tu k = ");
					scanf("%d",&k);
					if(k==0) break;
					addFirst(&head,&tail,k);
				}
				break;
			}
            case '2': {

				system("cls");
				printf("\nPut 0 to Out 2");
				while(1) {
	                printf("\naddTail: phan tu k = ");
	              //fflush(stdin);
	              	scanf("%d",&k);
	              	if(k==0) break;
	              	addTail(&head,&tail,k);
				}
				break;
			}
			case '3': {

				system("cls");
				printf("\nPut 0 to Out 3");
				while(1) {
	                printf("\naddMid: phan tu k = ");
	              //fflush(stdin);
	              	scanf("%d",&k);
	              	if(k==0) break;
	              	printf("\naddMid: vao vi tri position = ");
	              	scanf("%d",&position);
	              	addMid(&head,position,k);
				}
				break;
			}
			case '4': {
				system("cls");
				printf("\ndeleFirst: phan tu dau: ");
				deleFirst(&head);
				printf("\nDone");
				system("pause");
				break;
			}
			case '5': {
				system("cls");
				printf("\ndeletail: phan tu cuoi: ");
				deleTail(&head,&tail);
				printf("\nDone");
				system("pause");
				break;
			}

			case '6': {

				system("cls");
				
	                printf("\ndeleMid: phan tu  ");
	              //fflush(stdin);
	              	scanf("%d",&k);
	              	printf("\ndeleMid: vao vi tri position = ");
	              	scanf("%d",&position);
	              	deleMid(&head,position - 1);
				break;
			}
			case '7': {
				system("cls");
				printList(head);
				printf("\n");
				system("pause");
				break;
			}
			case '8': {
				system("cls");
				detroyList(head);
				return 0;
			}
        }
    }
}
