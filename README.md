# weighing
# c program
# Given N weights with positive integer weights, let's use these weights to find the smallest non-measurable positive integer weight! 무게가 양의 정수인 N개의 저울추가 주어질 때, 이 추들을 사용하여 측정할 수 없는 양의 정수 무게 중 최솟값을 구해보자!
#include <stdio.h>
int main(void){
	int n,temp,a=1;
	int input[1001];
	int i,j;
	scanf("%d",&n);
	for(i=0;i<n;i++){
		scanf("%d",&input[i]);
	}
	for(i=0;i<n;i++){
		for(j=0;j<n-(i+1);j++){
			if(input[j]>input[j+1]){
				temp=input[j];
				input[j]=input[j+1];
				input[j+1]=temp;
			}
		}
	}
	for(i=0;i<n;i++){
		if(a<input[i]){
			break;
		}
		else{
		a+=input[i];}
	}
	printf("%d",a);
	return 0;
}
# python
def solution():
    N=int(input())
    num=list(map(int,input().split()))
    num.sort()
    a=1
    for i in range(N):
        if a<num[i]: #1보다 큰수가 나오면 멈추고 아니라면 1부터 하나씩 증가한다
            break
        a+=num[i] #1씩 증가한 수에 1을 더해서 최솟값을 구함(a를 1로 둔이유)
    return a
print(solution())
#input--> 7  3 1 6 2 7 30 1
#result--> 21
