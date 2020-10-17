#include <bits/stdc++.h>
using namespace std;
string st;
stack<string> s;
long long length,i;

bool checkOperator(char ch){ 
  switch (ch) { 
  case '-': 
  case '+': 
  case '/': 
  case '*': 
    return true; 
  } 
  return false; 
}

int main(){

	cout<<"Enter the string for conversion:\n";
	cin>>st;

	length = st.size(); 

	for (i = length - 1; i >= 0; i--) { 	

		if (checkOperator(st[i])) { 
  
      			string s1 = s.top(); 
			s.pop(); 

      			string s2 = s.top(); 
			s.pop(); 
   
      			string temp = s1 + s2 + st[i]; 
  
      			s.push(temp); 
    		} 
  
    		else { 
      			s.push(string(1, st[i])); 
    		} 

  	} 

	cout<<"Postfix expresssion is:\n"<<s.top()<<"\n";

	return 0;

}