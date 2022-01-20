## STL
(under active building)

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
using namespace std;

bool f(int x, int y)
{
    return x > y;
}
// comparator funtion, used to sort in descreasing order if returns x>y.

int main()
{
    vector<int> v;
    // v is a vector having 'n' elements with all being zeros.

    // Insert values into vector
    v.push_back(2);
    v.push_back(7);

    // TAKING INPUT
    int n;
    cin >> n;
    vector<int> v(n); // v = {0,0,0,0,...}
    for (int &x : v)
        cin >> x;

    // INITIALIZE
    vector<int> arr(5, 3); // {3,3,3,3,3}

    vector<string> v(4, "hello World");
    // intialising the vector with 4 hello World's

    vector<int> v = {1, 2, 3, 4, 5};
    auto it = v.end();
    // does not point to last element of array i.e 5, but address after '5'

    v.rend();
    // points to address before '1'

    v.rbegin();
    // reverseBegin, points to 5

    v.cbegin() OR v.cend();
    // if you do not want to change iterator, 'c' - constatnt

    v.back();
    // to get the last element, even if you do not know the size

    v.erase(v.begin());
    // deletes first element

    v.erase(v.begin() + (any number));
    // deletes [any number] element

    v.erase(v.begin() + 2, v.begin() + 4);
    // [ele2, ele4) - does not delete the last element it points to

    v.size();
    // return the size of vector in integers

    v.pop_back();
    // erase the last element
    // size is automatically dec/inc after the operations

    v1.swap(v2);
    // = swap v1 <=> v2.

    v.clear();
    // earse the entire vector, no element.v.empty() - bool, kind of isEmpty(), check if its empty or not

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
    swap(a, b);

    // calling the reverse function
    reverse(v.begin(), v.end());

    // calling the rotate function
    rotate(v.begin(), v.begin() + 1, v.end());

    // sorting the container(Vector)
    // it is based on intro sort(quick sort + heap sort + insertion sort)
    // O(NlogN), else use merge sort
    // in ascending order
    sort(v.begin(), v.end());

    // in descending order
    sort(v.begin(), v.end(), greater<int>());

    sort(v.begin(), v.end(), f);
    // here f is a comparator function. Refer LIST section for more on comparator.

    // CONVERT ARRAY TO VECTOR
    int arr[] = {2, 46, 15, 63, 5, 96};
    int size = sizeof(arr) / sizeof(arr[0]);
    std::vector<int> vect(arr, arr + size);

    // REMOVE DUPLICATES USING SET
    set<int> s;
    for (int i : vect)
        s.insert(i);
    vect.assign(s.begin(), s.end());

    // remove duplicates without sorting
    unordered_set<int> s;
    for (int i : vect)
        s.insert(i);
    vect.assign(s.begin(), s.end());

    // A FUNCTION TO PRINT ANY VECTOR USING printV(vec)
    void printV(vector<int> v)
    {
        for (int x : v)
            cout << x << ' ';
        cout << endl;
    }

    // Taking values
    int n;
    cin >> n;
    vector<int> B(n, 0);
    for (int i = 0; i < n; i++)
        cin >> A[i];

    // SOME EXAMPLES
    vector<int> vec(5, 100);
    // initialize with 5 element, each 100. // 100, 100, 100, 100, 100
    vector<int> v(2, 100);          // 100, 100
    v.insert(v.begin(), 300);       // 300, 100, 100
    v.insert(v.begin() + 1, 2, 11); // 300, 11, 11, 100, 100

    vector<int> v1(2, 50);                     // {50, 50}
    v.insert(v.begin(), v1.begin(), v1.end()); // v = 50, 50, 300, 11, 11, 100, 100
                                               // copy the 'v1' vector to 'v'.

    vector<vector<int>> arr2(2, vector<int>(4, 10));
    for (int i = 0; i < 2; i++)
    {
        for (int j = 0; j < 4; j++)
            cout << arr2[i][j] << " ";
        cout << endl;
    }
    // 10 10 10 10
    // 10 10 10 10

    vector<int> v = {2, 3, 4};
    cout << v.capacity() << " " << v.size() << endl; // 3 3
    v.push_back(5);
    cout << v.capacity() << " " << v.size() << endl; // 6 4
    // capacity is the total size of the vector after push_back.

    // NEXT() AND PREV()
    vector<int> ar = {1, 2, 3, 4, 5, 6};
    auto p1 = ar.begin();   // 1
    auto p2 = ar.end();     // an address after '6'
    auto it1 = next(p1, 3); // move 3 step from start 2->3->4
    auto it2 = prev(p2, 3); // move 3 step from end towards start, 6->5->4
    auto it3 = ar.begin();
    advance(it3, 2); // advance is use to increment the value by certain number
    cout << "The position of new iterator using next() is : ";
    cout << *it1 << " ";
    cout << endl;

    cout << "The position of new iterator using prev()  is : ";
    cout << *it2 << " ";
    cout << *it3 << " ";
    cout << endl;

    // print the vector
    // iterator i in a for loop, this syntax cannot be used everywhere.
    for (auto i : v)
        cout << i << " ";
    cout << endl;

    // here v is {2,5,100,100,100,123}
    // to find the first element >= to 100 in a vector, O(logN)
    vector<int>::iterator it = lower_bound(A.begin(), v.end(), 100);
    auto it = lower_bound(v.begin(), A.end(), 100);
    // both the above lines are same

    auto it2 = upper_bound(A.begin(), A.end(), 100);
    // first the element strictly > 100 //123

    for (auto x : A)
    {
        x--;
        cout << x << " ";
    }
    // this x-- wont work here, cant change the value, if you want to change value and also iterate, use int &x not x.
    // not using &x does change value but not of original vector, just for this printing purpose

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

    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
