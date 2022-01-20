```C++
#include <iostream>
#include <vector>
#include <algorithm>
#include <set>
#include <bits/stdc++.h>

//  Using SET, we have unarranged list, and we want to do operations on it.
//  In set, only unique elements are stored
//  Implemented using BST
//  Modification of elements is allowed
//  Stores element in sorted order
//  in a vector<vector>int> > matrix, matrix.size() gives size of row only.

using namespace std;

void set_func()
{
    set<int> S;
    S.insert(5);
    S.insert(1);
    S.insert(1); // duplicates are not stored, ignores it.
    S.insert(2); // 1,2,5 [Set automatically arranges itself]
    // automatically sorted in ascending order in logN time. You cannot insert element at your wished place.

    // Print
    for (auto x : S)
        cout << x << " "; // can use 'int' in place of auto.
    cout << endl;

    // printing the set, second way
    set<int, greater<int>>::iterator itr;
    for (itr = s.begin(); itr != s.end(); itr++)
        cout << *itr << " ";
    cout << endl;
    // to save time from sorting the elements, we use set, which internally sorts the elements for us.
    // as general sorting is NlogN, takes time.

    auto it = S.find(2);
    // now 'it' points to ele 2, if 2 is not present, it will point to S.end()
    if (it == S.end())
        cout << "Element not present " << endl;
    // and it has value NULL, 0.
    else
        cout << "Element present is " << *it << endl;

    auto it2 = S.lower_bound(1);
    // gives iterartor to the first ele >= to number present in ()
    // as Set is already sorted, we dont have to A.begin(), A.end()
    cout << *it2 << endl;

    auto it3 = S.upper_bound(1); // stricly first '>' ele after 1
    cout << *it3 << endl;
    // content in '()' need not be element, it can be any number we want to compare.
    // if not bound is found, iterartor returns S.end();

    S.erase(1);
    // in logN time.
    // Set is more powerful than vectors

    S.count(9);
    // "count" function returns bool value in O(log n) tim

    int cnt = S.count(1); 
    // Counts occurance, 1 if present else 0.

    S.clear(); // deletes everything
    auto it = st.find(3);
    
    S.erase(it);
    // in constant time
    
    S.erase(it1, it2) 
    // deletes in range from [it1, it2), last one is excluded
}

void unordered_set()
{
    // Implemented using BST
    // Modification of elements is allowed
    // declaration
    unordered_set<int> ust;

    // inserting elements takes O(1) time
    ust.insert(1);
    ust.insert(7);
    ust.insert(8);
    ust.insert(2);
    ust.insert(5);

    // printing the set
    unordered_set<int>::iterator itr;
    for (itr = ust.begin(); itr != ust.end(); itr++)
    {
        cout << *itr << " ";
    }
    cout << endl;

    // finding any elements require O(1)
    // "find" function returns the iterator in O(1)
    cout << "Print 5 if present ";
    cout << *ust.find(5) << endl;
    // "count" function returns bool value in O(1) time
    cout << "Is 9 present in the set? " << ust.count(9) << endl;

    // deleting all elements in the set
    cout << "Is the set empty? " << ust.empty() << endl;
    ust.clear();
    cout << "Is the set empty now? " << ust.empty() << endl;
}

int32_t main()
{
    // unordered_set();
    set_func();
    return 0;
}