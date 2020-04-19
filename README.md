#include <iostream>
#include <cmath>
using namespace std;


int opredelitel(int n,int (&N)[10][10]){

int x,y,i,l,t,A[10][10];
l=0;

if (n>2){for (i=0;i<n;i++){t=N[i][0];


for (y=0;y<10;y++){for (x=0;x<10;x++){A[y][x]=N[y][x];}}
for (x=i;x<n;x++){for (y=0;y<n;y++){A[x][y]=A[x+1][y];}}
for (y=0;y<n;y++){for (x=0;x<n;x++){A[x][y]=A[x][y+1];}}



l=l+pow(-1,i)*t*opredelitel(n-1,A);}
}

if (n==2){l=N[0][0]*N[1][1]-N[0][1]*N[1][0];}

return l;}






int main()
{int n,i,j,N[10][10];

cin>>n;

for (i=0;i<n;i++){for (j=0;j<n;j++){cin>>N[i][j];}}

if (n==1){cout<<N[0][0];} else
cout<<opredelitel(n,N);

return 0;
}
