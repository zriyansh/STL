```C++
#include<iostream>
#include<list>


using namespace std;
int main(){

    list<int> ls;
    // alternate syntax
    list<int> lss = {1,2,3,4,5};

    ls.push_back(2); //{2}
    ls.emplace_back(4); //{2, 4}
    ls.push_front(5); // {5, 2, 4} // this is not present in a vector
    ls.emplace_front(3); //{3, 5, 2, 4} //
    ls.pop_back();
    ls.pop_front();
    
    // First and last element of list
    ls.front();
    ls.back();

    ls.reverse();
    ls.sort();
    ls.splice(i,ls);//takes the whole list 'ls' and adds it at the iterator 'i' position mentioned

    // Merging two SORTED lists into one
    l1.merge(l2); // assume l1 and l2 as 2 lists, l2 gets appended to l1
    cout<<"Merged List"<<endl;

    // MERGE USING COMPARATOR
    // comparator function – It is a binary predicate which takes two values of the same type that of those contained in the list,
    bool comparator(int first, int second){
    return first < second;
    }

    list<int> list1 = { 1, 70, 80 };
    list<int> list2 = { 2, 3, 4 };
  
    // merge and sort
    list1.merge(list2, comparator); // 1,2,3,4,70,80

    // Print the list
    for(auto it : list1){
        cout<< it <<endl;
    }

  // Copy list
  list<int> lis1={1,2,3,4,5,6};
	list<int> lis2;
	lis2.assign(lis1.begin(),lis1.end()); //copies lis1 to lis2
	
  // Print list
  cout<<"List element are : \n";
	for(auto i=lis2.begin();i != lis2.end(); i++)
  cout<<*i<<endl;



 list<int> mylist;
 list<int> :: iterator it1, it2;
 
 for (int i = 1; i < 10; ++i) 
 mylist.push_back(i * 1);
 
 it1 = it2 = mylist.begin();
 advance (it2, 6); // Moves it2 6 steps ahead



  list<int> l;
  list<int>:: iterator i=l.begin();
  
  //inserts the Elements just before the position of iterator
  l.insert(i,10);
  i++;
  
  l.insert(i,20); // 20,10
  cout<<"Elements after inserting"<<endl;
  i++;

  l.insert(i,5,25); // 20,10, 25,25,25,25,25
  //The first Parameter is the position of the iterator,second is the count ...
  //number of times you want to insert the element, third argument is the value

  cout<<*i; // now i = 7, pointing to 7th index
  l.insert(i,l.begin(),l.end());
  //This means that insert all the Elements from start to end before the iterator 'i' position
  //The start and stop (2nd and 3rd parameters can be varied).
  
//rest functions same as vector, does not auto sort elements.
//begin, end, rbegin, rend, clear, insert, size, swap
}