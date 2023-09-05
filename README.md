# reverse-string-using-stack

#include <stdio.h>
#include<stdlib.h>
#include<string.h>
typedef struct stack{
    int top;
    int size;
    char *arr;
}stack;



stack* create(int capacity){
    struct stack* st = (stack*)malloc(sizeof(stack));
    st->top = -1;
    st->size = capacity;
    st->arr = (char*)malloc(st->size*sizeof(char));
    return st;
}

int isEmpty(stack* st){
    if(st->top==-1){
        return 1;
    }
    return 0;
}

int isFull(stack* st){
    if(st->top == st->size-1){
        return 1;
    }
    else{
        return 0;
    }
}


void push(stack* st,char val){
    if(isFull(st)){
        return;
    }
    else{
        st->top ++;
        st->arr[st->top] = val;
    }
}


char pop(stack* st){
    if(isEmpty(st)){
        return 0;
    }else{
    char temp = st->arr[st->top];
    st->top--;
    return temp;    
    }
}


int main(){
	char name[] = "avinash";
    int n = strlen(name);
    stack* st = create(n);
    for(int i=0;i<n;i++){
    push(st,name[i]);
    }
    
    for(int j=0;j<n;j++){
    printf("%c",pop(st));
    }


return 0;
}

















