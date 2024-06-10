# Max-sum-array
Find the maximum sum present in a given subarray with brute force and optimal using kadane's algorithm
//Kadane's algorithm
#include<iostream>
using namespace std;

int main(){
	int n;
	cout<<"Enter the size: ";
	cin>>n;
	int arr[n];
	for(int i=0;i<n;i++){
		cin>>arr[i];
	}
	
	//TC:O(n^2)
	int res=arr[0];
	for(int i=0;i<n;i++){
		int curr_sum=0;
		for(int j=i;j<n;j++){
			curr_sum+=arr[j];
			res=max(res,curr_sum);
		}
	}
	cout<<"Maximum sum is: "<<res;
	
	//TC:O(n)
	int res=arr[0];
	int maxEnding=arr[0];
	for(int i=1;i<n;i++){
		maxEnding=max(maxEnding+arr[i],arr[i]);
		res=max(res,maxEnding);
	}
	cout<<"Max sum is: "<<res;
}
