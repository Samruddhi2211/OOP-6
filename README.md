# OOP-6
Experiment No.7
Write a program in C++ to use map associative container. The keys will be the names of states,
and the values will be the populations of the states. When the program runs, the user is
prompted to type the name of a state. The program then looks in the map, using the state name
as an index, and returns the population of the state.
#include <iostream>
#include <map>
#include<string>
using namespace std;
int main()
{
string state;
int population;
char ans = ‘y’;
int choice;
map<string,int> m;
map<string,int>::iterator i;
do
{
cout << "\n Main Menu";
cout << "\n1. Insert an element";
cout << "\n2. Display";
cout << "\n3. Search an state";
cout << "\n Enter your choice: ";
cin >> choice;
switch (choice)
{
case 1:cout << "\n Enter the name of state: ";
cin >> state;
cout << "\n Enter the population(in Cr): ";
cin >> population;
m.insert(pair<string,int>(state,population));
break;
case 2:cout << "State and Populations are: ";
for (i = m.begin(); i != m.end(); i++)//i is for iterator
cout <<"[" <<(*i).first << ", "<<(*i).second<<"] ";
break;
case 3:cout << "\n Enter the name of state for searching its population: ";
cin >> state;
if(m.count(state)!=0) // first represents key and second represents valuecout << "Population is " << m.find(state)->second<<”Cr”;
else
cout << "State is not present in the list" << endl;
break;
}
cout << "\n Do you want to continue?(y/n): ";
cin >> ans;
} while (ans == 'y' || ans == 'Y');
return 0;
}
Output
 Main Menu
1. Insert an element
2. Display
3. Search an state
 Enter your choice: 1
 Enter the name of state: Maharashtra
 Enter the population(in Cr): 126
 Do you want to continue?(y/n): y
 Main Menu
1. Insert an element
2. Display
3. Search an state
 Enter your choice: 1
 Enter the name of state: Gujrat
 Enter the population(in Cr): 72
 Do you want to continue?(y/n): y
 Main Menu
1. Insert an element
2. Display
3. Search an state
 Enter your choice: 1
 Enter the name of state: Punjab
 Enter the population(in Cr): 4
 Do you want to continue?(y/n): y
 Main Menu
1. Insert an element
2. Display
3. Search an state
 Enter your choice: 2
 State and Populations are: [Maharashtra, 126] [Gujrat, 72] [Punjab, 4]
Do you want to continue?(y/n): y
 Main Menu
1. Insert an element
2. Display
3. Search an state
 Enter your choice: 3
Enter the name of state for searching its population: Maharashtra
Population is 126 Cr
Do you want to continue?(y/n): n
