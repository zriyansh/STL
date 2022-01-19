# STL

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

  </p>
</details>
