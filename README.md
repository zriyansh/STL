## STL

## Header files
`#include <iostream>`<br>
`#include <algorithm>`<br>
`#include <array>`<br>
`#include <vector>`<br>
`#include <set>`<br>
`#include <stack>`<br>
`#include <queue>`<br>
`#include <deque>`<br>
`#include <map>`<br>
`#include <unordered_map>`<br>
`#include <list>`<br>

Or simply use <br>
`#include<bits/stdc++.h>`

# VECTOR

<details>
  <summary>VECTOR</summary>
  <p>


```C++

int main() {
    vector<int> v;
     // Insert values into vector
    v.push_back(2);
    v.push_back(7);
   
    
    // print the vector
    // iterator i in a for loop, this syntax cannot be used everywhere. 
    for (auto i : v) 
        cout << i << " "; 
    cout << endl;
    
    // binary search - to search if an element is present
    cout << "Check if 6 is present in vector ";
    cout << binary_search(v.begin(), v.end(), 6) << endl; // iterates from begin to end and finds 6, if present

    // lower bound:- The element just greater than given element
    cout << "The lower bound for 5 is ";
    cout << lower_bound(v.begin(), v.end(), 5) - v.begin() << endl;

    // upper bound:- The element just smaller than the given element
    cout << "The upper bound for 5 is ";
    cout << upper_bound(v.begin(), v.end(), 5) - v.begin() << endl;

    // maximum of two number
    int a = 8, b = 10;
    cout << "Maximum of " << a << " and " << b << " is " << max(a, b) << endl;

    // minimum of two no.
    cout << "Minimum of " << a << " and " << b << " is " << min(a, b) << endl;

    // swap function to replace the value among themselves
    cout << "Earlier a=" << a << " and b=" << b << endl;
    swap(a, b);
    cout << "Now a=" << a << " and b=" << b << endl;
    
    // calling the reverse function
    reverse(v.begin(), v.end());
  
    // calling the rotate function
    rotate(v.begin(), v.begin() + 1, v.end());
   
    // sorting the container
    // it is based on intro sort(quick sort + heap sort + insertion sort)
    sort(v.begin(), v.end());
    
    return 0;
    }
```

[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#stl)
</p>
</details>

<!-- END OF VECTOR -->

# ARRAY

<details>
  <summary>ARRAY(click me)</summary>
  <p>


```C++
    int main(){

    // declaration
    array<int, 4> a;

    // assigning values
    for (int i = 0; i < 4; i++)
    cin >> a[i];
    
    // declaration and assigning value
    array<int, 4> a = {1, 2, 3, 4};

    // printing the array
    for (int i = 0; i < 4; i++)
        cout << a[i] << " ";
    cout << endl;

    // print the array using auto keyword
    for (auto i : a)
        cout<< i;
    cout<<endl;

    // finding the size of the array
    cout << a.size() << endl;

    // accessing any element at given potion
    cout << a[3] << " " << a.at(3) << endl;

    // checking if the array is empty
    cout << "Is array empty ? " << a.empty() << endl;

    // excessing first and last element
    cout << a.front() << " " << a.back() << endl;
    
    return 0;
    }

```

[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#stl)
</p>
</details>
    
    
    
    
 # LIST

<details>
  <summary>LIST</summary>
  <p>


```C++
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


```
    
[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#stl)

  </p>
</details>

    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
