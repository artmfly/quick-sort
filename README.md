#include <iostream>
#include <algorithm>
using namespace std;
int* Qucksort(int left, int right,int list[]){
    if(left < right){
        int a = list[(left + right) / 2];
        int start = left;
        int end = right;
        while(start < end){
            while(list[start] < a){
                start += 1;
            }
            while(list[end] > a){
                end -= 1;
            }
            if(start <= end){
                swap(list[start++], list[end--]);
            }
        }
        Qucksort(left, end, list);
        Qucksort(start, right, list);
    }
    else{
        return list;
    }
}
int main()
{
    int n, x, y;
    cin >> n;
    int list[n];
    for(int i = 0; i < n; i++){
        cin >> list[i];
    }
    Qucksort(0, n - 1, list);
    for(int i = 0; i < n; i++){
        cout << list[i] << " ";
    }
}
