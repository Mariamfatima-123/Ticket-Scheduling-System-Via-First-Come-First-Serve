#include"stdafx.h"
#include<iostream>
using namespace std;
void Waiting_Time(int processes[], int n, int bt[], int wt[])
{
wt[0] = 0;
for (int i = 1; i < n ; i++ )
wt[i] = bt[i-1] + wt[i-1] ;
}
void TurnAround_Time( int processes[], int n, int bt[], int wt[], int tat[])
{
for (int i = 0; i < n ; i++)
tat[i] = bt[i] + wt[i];
}
void Average_Time( int processes[], int n, int bt[])
{
int wt[n], tat[n], total_wt = 0, total_tat = 0;
Waiting_Time(processes, n, bt, wt);
TurnAround_Time(processes, n, bt, wt, tat);
cout << "P"<< " B-time " << " W-time " << " TA-time" <<endl;
for (int i=0; i<n; i++)
{
total_wt = total_wt + wt[i];
total_tat = total_tat + tat
 cout << " " << i+1 << "\t" << bt[i] <<"\t " << wt[i] <<"\t\t " << tat[i] <<endl;
}
cout << "Average waiting time = " << (float)total_wt / (float)n <<endl;
cout << "Average turn around time = " << (float)total_tat / (float)n <<endl;
}
int main()
{
int processes[] = { 1, 2, 3, 4 ,5};
int n = sizeof processes / sizeof processes[0];
int burst_time[] = {6, 2, 8, 3, 4};
Average_Time(processes, n, burst_time);
system("pause");
return 0;
}
