# THR-Strukdat

THR STRUKDAT

#include <stdio.h>
#define MAX 5 

This includes the standard input/output library and defines the maximum array size as 5.

int stack[MAX], top = -1;
int i, x;

An array stack is created, and top is set to -1 to indicate it is empty. Variables i and x are used for looping and input.

printf("=== STACK ===\n");
printf("Masukkan Antrian :\n");

Displays instructions for entering stack data.

for(i = 0; i < MAX; i++) {
    scanf("%d", &x);
    stack[++top] = x;
}

takes 5 inputs and pushes them into the stack (LIFO).

printf("Antrian terakhir : %d\n", stack[top--]);

Displays and removes the last element from the stack.

int queue[MAX], front = 0, rear = -1;

Creates a queue with front and rear.

printf("\n=== QUEUE ===\n");
printf("Masukkan Antrian:\n");

Displays instructions for queue input.

for(i = 0; i < MAX; i++) {
    scanf("%d", &x);
    queue[++rear] = x;
}

Adds elements to the queue from the rear (FIFO).

printf("Yang Main : %d\n", queue[front++]);

Displays and removes the first element in the queue.

int deque[MAX];
int frontD = 0, rearD = -1;
char tipe;

Creates a deque with front and rear pointers, and a variable for type (VIP or Normal).

printf("\n=== DEQUE ===\n");
printf("Masukkan Antrian (V=VIP, N=Normal):\n");

Displays instructions for deque input.

for(i = 0; i < MAX; i++) {
    scanf("%d %c", &x, &tipe);

Takes input of player number and type.

if(tipe == 'V' || tipe == 'v') {
    for(int j = rearD; j >= frontD; j--) {
        deque[j+1] = deque[j];
    }
    deque[frontD] = x;
    rearD++;
}

If the player is VIP, all elements are shifted right and the VIP is inserted at the front

else {
    deque[++rearD] = x;
}

Normal players are added to the rear of the deque.
