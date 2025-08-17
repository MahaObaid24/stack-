#include <iostream>
#include <stack>
#include<cctype>
using namespace std;
void evaluate(string arr){
    stack<int>s;
    for(char c : arr){
        if(isdigit(c)){
            s.push(c - '0');
        }
        else{
            int val2 = s.top();s.pop();
            int val1 = s.top();s.pop();
            
            switch(c){
                case '+': s.push(val1+val2) ; break;
                case '-': s.push(val1-val2) ; break;
                case '*': s.push(val1*val2) ; break;
                case '/': s.push(val1/val2) ; break;
            }
        }
    }
    
    cout<<s.top();
}
int main()
{
    string arr = "23*54*+";
    evaluate(arr);

    return 0;
}
