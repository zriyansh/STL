## STL
(under active building)

What is C++ STL? <br>
Standard Template Library found in C++.
No, STL is your best friend (okay 2nd best) that helps you unconditionally especially while you are solving questions on LeetCode or during contests. 

# VECTOR

<details>
  <summary>VECTOR (click here)</summary>
  <p>


```C++


using namespace std;

bool f(int x, int y)
{
    return x > y;
}
// comparator funtion, used to sort in descreasing order if returns x>y.

int32_t main(){
	// We use int32_t for faster compilation and also because main() should always return value 
	// accoring to 32bit system, even 64bit system use 32bit int. 	  

	ios_base::sync_with_stdio(0); 
	// it turns off buffer synchronization between the cin stream and C-style stdio tools (like scanf or gets), 
	// so cin works faster, but you can't use it simultaneously with stdio tools.
	  
	cin.tie(NULL);
	// This line unties cin from cout — by default the cout buffer flushes each time when you read something from cin.
	  
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
  <summary>ARRAY</summary>
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

# STACK

<details>
  <summary>STACK</summary>
  <p>


```C++


// Integer Stack
void stack_int()
{
    stack<int> st;
    st.push(1);    // 1
    st.push(2);    // 2, 1
    st.push(3);    // 3, 2, 1
    st.push(3);    // 3, 3, 2, 1
    st.emplace(5); // 5, 3,3,2,1

    cout << st.top(); // cant use st[2] notation, 5

    st.pop(); // 5

    cout << st.top();           // 3
    cout << st.size();          // 4
    cout << st.empty() << endl; // empty or not

    stack<int> st1, st2;
    st1.swap(st2);
}

// String Stack
void stack_string()
{
    stack<string> st;

    // assigning value
    st.push("abc");
    st.push("xyz");
    st.push("pqr");

    // printing our stack
    cout << "top element is " << st.top() << endl;

    // size of stack
    cout << "size of stack is " << st.size() << endl;

    // stack is empty or not
    cout << "Is the stack empty?" << st.empty() << endl;

    // removing the top element
    st.pop();
    cout << "Now the top is " << st.top() << endl;

    // printing the complete stack
    // inserting new elements
    st.push("Computer");
    st.push("Science");
    st.push("Engineering");
    int n = st.size();
    cout << "The complete stack is ";
    for (int i = 0; i < n; i++)
    {
        cout << st.top() << " ";
        st.pop();
    }
    cout << endl;
}

int main()
{
    stack_string();

    // stack doesnt allow access to anything other than top.
    // doesnot have iterators or begin or end. Just these functions.
}


```


[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#stl)
  </p>
</details>

    
# SET

<details>
  <summary>SET</summary>
  <p>


```C++


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

    S.count(9);
    // "count" function returns bool value in O(log n) time

    int cnt = S.count(1); 
    // Counts occurance, 1 if present else 0.

    S.clear(); // deletes everything
    auto it = st.find(3);
    
    S.erase(1);
    // in logN time.
    // Set is more powerful than vectors
    
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

```


[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#stl)
  </p>
</details>	  
    
	  
	  
# MULTISET

<details>
  <summary>MULTISET</summary>
  <p>


```C++
using namespace std;

int main()
{
    multiset<int> ms;
    ms.insert(1);
    ms.insert(1);
    ms.insert(1);

    int cnt = ms.count(1);

    ms.erase(1); // eases all 1's

    for (auto x : ms)
        cout << x << endl;
    cout << cnt;

    ms.insert(1);
    ms.erase(ms.find(1)); // only a single 1 is erased that it finds first

    ms.erase(ms.find(1), ms.find(1) + 2); // move iterator in a range to delete 1's.

    // rest same as set, only it stores duplicate element too.
    // lower_bound, upper_bound also available.
    // stores in sorted way

    // UNORDERED SET
    unordered_set<int> us;
    // upper_bound and lowe_bound do not work, rest same.
    //  collisions may happen, so you get wrong answers but else its faster.
    //  does not store in sorted way.
    //  O(1) avg case.
}


```


[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#stl)
  </p>
</details>	  
	  
	  
	  
	  
	  
	  
	  
    
# QUEUE

<details>
  <summary>QUEUE</summary>
  <p>


```C++
using namespace std;

void queue_func()
{
    queue<int> q;
    q.push(1);    // 1
    q.push(12);   // 1, 12
    q.emplace(4); // 1, 12, 4

    q.back() += 5;
    cout << q.back() << endl; // 9, adds 5 to last element of queue

    q.pop(); // 12, 9, '1' gets deleted
    q.size();
    q.empty();

    cout << q.front(); // prints 12, NOT q.top()

    // printing the entire queue
    cout << "Printing the entire queue : ";
    int n = q.size();
    for (int i = 0; i < n; i++)
    {
        cout << q.front() << " ";
        q.pop();
    }
    cout << endl;

    // size, swap empty same as stack
    // queue, stack, dequeue are all containers.
}

// it works on max heap and min heap
// i.e. it stores values in sorted order either increasing or decreasing

void priority_queue_func()
{
    priority_queue<int> pq; // Creates a max heap, decreaasing order

    priority_queue<int, vector<int>, greater<int>> pq_min; // Creates a min heap, increasing order

    pq.push(5);     // 5
    pq.push(2);     // 5,2
    pq.emplace(11); // 11,5,2
    pq.push(8);     // 11,8,5,2

    cout << pq.top() << endl; // 11

    pq.pop(); // 11 removed

    cout << pq.top(); // 8

    // size swap empty same as others
    // uses properties of queue and stacks
    // priority queue stores element in sorted fasion, descending

    // Minimun Heap, to invert priority_queue funtion, and sort in ascending order.
    priority_queue<int, vector<int>, greater<int>> pq1;

    // greater<int> - reverses the fasion of storing the elements
    pq1.push(5);     // 5
    pq1.push(2);     // 2,5
    pq1.push(8);     // 2,5,8
    pq1.emplace(10); // 2,5,8,10

    // now elements are in Ascending order
    cout << pq1.top(); // 2

    // printing the (max heap)
    cout << "Printing the maxi ";
    int n = pq1.size();
    for (int i = 0; i < n; i++)
    {
        cout << pq1.top() << " ";
        pq1.pop();
    }
}

int main()
{
    // queue_func();
    priority_queue_func();
    return 0;
}



```


[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#stl)
  </p>
</details>

    
# DEQUE

<details>
  <summary>DEQUE</summary>
  <p>


```C++
using namespace std;

// doubly ended queue
int main()
{
    // declaration
    deque<int> dq;

    // assigning value
    // we can enter value in doubly ended queue both from front and back
    dq.push_back(1);
    dq.emplace_back(2);
    dq.push_front(3);    //{3,1,2}
    dq.emplace_front(3); //{3,3,1,2}
    dq.pop_back();       // removes 2
    dq.pop_front();      // removes front element 3

    // printing the deque
    for (auto i : dq)
        cout << i << " ";
    cout << endl;

    // accessing the ith element from a deque
    cout << dq[1] << " " << dq.at(1) << endl;

    // get front and back elements
    cout << "Front and back elements are ";
    cout << dq.front() << " and " << dq.back() << endl;

    // to check if our deques is empty or not;
    cout << "Is the deque empty? " << dq.empty() << endl;

    // first and last+1 iterators
    cout << "First and last element using pointers" << endl
         << *dq.begin() << " " << *(dq.end() - 1) << endl;

    // size of the deque
    cout << "The size of deque is " << dq.size() << endl;

    // deleting all elements of deque or selection of elements
    dq.erase(dq.begin() + 2, dq.end());

    // delete all
    dq.erase(dq.begin(), dq.end());
    cout << "\nAfter deleting all elements" << endl;

    // has all vector functionalities inherited
    // deque can access front elements directly.

    return 0;
}


```


[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#stl)
  </p>
</details>    
    
    
# PAIR

<details>
  <summary>PAIR</summary>
  <p>


```C++
using namespace std;
int main()
{

    pair<int, int> p1 = {2, 4};
    cout << p1.first << " " << p1.second << endl;

    pair<int, pair<int, int>> p2 = {3, {5, 6}};
    cout << p2.first << " " << p2.second.first << endl;

    pair<int, int> arr[] = {{1, 2}, {7, 8}};
    cout << arr[1].second << endl;
    // pairs can be applied anywhere, be it stacks, queues, etc

    vector<pair<int, int>> v;
    v.push_back({1, 2});
    v.emplace_back(1, 2); // does not need { } to insert elements at end

    pair<int, int> pair1, pair3; // creats pair of integers
    pair<int, string> pair2;     // creates pair of an integer an a string

    pair1 = make_pair(1, 2);              // insert 1 and 2 to the pair1
    pair2 = make_pair(1, "Studytonight"); // insert 1 and "Studytonight" in pair2
    pair3 = make_pair(2, 4);
   
    cout << pair1.first << endl;  // prints 1, 1 being 1st element of pair1
    cout << pair2.second << endl; // prints Studytonight

    if (pair1 == pair3)
        cout << "Pairs are equal" << endl;
    else
        cout << "Pairs are not equal" << endl;

    // FIND THE INTERVAL IN WHICH A NUMBER X LIES.
    set<pair<int, int>> S1;
    S1.insert({2, 4});
    S1.insert({10, 20});
    S1.insert({21, 100});
    S1.insert({200, 400});
    
    // A pair {a,b} is smaller than {c,d} iff (a<b) OR (a==b && c<d)
    // These are non-overlapping pairs.
    // pairs are also sorted automatically in a set.

    int point = 411;
    auto it4 = S1.upper_bound({point, INT_MAX});

    if (it4 == S1.begin())
    {
        cout << "Out of range ";
        return 0;
    }
    // as if it4 == begin(), we cant go any step back, eg - if point =1, it doesnt lie in any pair.
    it4--;
    
    pair<int, int> current = *it4;
    if (current.first <= point && current.second >= point)
        cout << "Yes, we found the pair " << current.first << " " << current.second << endl;
    else
        cout << "Not found in given intervals.  ";
    
    // we use INT_MAX with pairs to compare them.
    // we did it4 --, so that first after comparing 50's upper bound, iterator will point to
   
    // {200,400} pair, then we come 1 step back to our required pair.
    // The values in pair X = {a,b} can be accessed using X.first and X.second.
}


```


[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#stl)
  </p>
</details>
    
    
# MAP

<details>
  <summary>MAP</summary>
  <p>


```C++
// Map is like a dictionary which holds data in key,value pairs

using namespace std;
int32_t main()
{
    map<int, int> M; // {key, value}

    M[1] = 30;
    M[10] = 300000;
    M[9090] = 8;
    // each of these mapping take logN time

    A.find();
    A.erase();
    // add(key,value) and erase(key,value) takes (logN) for ordered map, and (1) for unordered map.
    // We can map something to somthing in logN time, also for find and erase.

    map<char, int> cnt;
    // mapping char to int.
    string x = "Zriyansh aK";
    for (char c : x)
    {
        cnt[c]++;
        // building this takes time proportional to length
        // gives count of each occuring char in string x
    }
    cout << cnt['a'] << " " << cnt['z'] << endl;
    // OUTPUT, 2 0 - as 'a' occurs 2 times, 'z' none.

    // UNORDERED MAP
    map<char, int> M1;
    unordered_map<char, int> U1; // best (1), worst - (N)

    string s = " Zizriyansh Bhai ";

    for (char x : s)
        M1[x]++; // NlogN time, N is length of string for map

    for (char x : s)
        U1[x]++; // logN time for unordered MAP

    cout << M1['a'] << " " << endl;
    cout << U1['z'] << " " << endl;
    // count of a and z in string s

    map<int, pair<int, int>> m;

    map<pair<int, int>, int> m1;

    m[1] = 2;
    m.insert({3, 1});
    m.emplace({2, 1});

    // {
    //     {1,2},
    //     {2,1},
    //     {3,1}
    // }
    // In this fashion, maps are stored.

    for (auto x : m)
        cout << x.first << " " << x.second << endl;
    cout << m[1]; // value can be accessed.

    auto it = m.find(3);
    cout << *it.second;

    // Set is subset of Map.
    // map stores everything in sorted manner
    // map is sorted acc to keys.

    // erase, swap, size, empty bounds are same.

    unordered_map<string, double> umap;

    // inserting values by using [] operator
    umap["PI"] = 3.14;
    umap["root2"] = 1.414;
    umap["root3"] = 1.732;
    umap["log10"] = 2.302;
    umap["loge"] = 1.0;

    // inserting value by insert function
    umap.insert(make_pair("e", 2.718));

    cout << umap["PI"] << endl;    // 3.14
    cout << umap.at("PI") << endl; // 3.14

    // if you try to access a value for a key that doesn't exist,
    // a new value object that has been default constructed will be put into the map and it's reference returned.
    cout << umap["NA"] << endl; // 0
    // now NA is present in umap with value 0

    cout << endl;

    // find an element
    if (umap.find("na") == umap.end())
        cout << "Key not found\n";
    else
        cout << "Key Found\n";

    cout << endl;

    // Traversing an unordered map
    for (auto i : umap)
        cout << "key = " << i.first << " and its value = " << i.second << endl;

    map<string, string> companies;
    companies["Google"] = "Larry Page";
    companies["Facebook"] = "Mark Zuckerberg";
    
    // insertion can also be done as
    companies.insert(pair<string, string>("Xarvis Tech", "xarvis"));
    // or
    companies.insert(map<string, string>::value_type("Quora", "Adam D'Angelo"));
    // or even
    companies.insert(make_pair(string("Uber"), string("Travis Kalanick")));
    
    // Iterating the map
    map<string, string>::iterator itz;
    cout << "\nCompanies and founders" << endl;
    
    for (itz = companies.begin(); itz != companies.end(); itz++)
        cout << "Company: " << (*itz).first << "\t Founder: " << itz->second << endl;

    itz = companies.find("Google");
    cout << itz->second;

    // MULTIMAP
    // same as map, but can store duplicate values as well, sorted.
    //[] Operator cannot be used to insert values.
    //count() returns the number of times the key has appeared unlike map where count() returns either 0 or 1.
	  

    // UNORDERED MAP
    // does not store in sorted manner, takes O(1), collision might happen

    return 0;
}


```


[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#stl)
  </p>
</details>    
    

	  
# MISC

<details>
  <summary>MISC</summary>
  <p>


```C++
bool comp(pair<int, int> p1, pair<int, int> p2)
{
    if (p1.second < p2.second)
        return true;
    else if (p1.second == p2.second)
    {
        if (p1.first > p2.second)
            return true;
    }
    return false;
}
// this is a comparator function

using namespace std;
int32_t main()
{

    sort(a, a + n);               // [first, last) ascending order
    sort(a, a + n, greater<int>); // descending order, using comparator as used in PQ

    // CUSTOM SORT

    // sort a pair in asc acc to 2nd value in a pair, if same, soft them in desc acc to 1st value in pair
    pair<int, int> a[] = {{1, 2}, {2, 1}, {4, 1}};
    sort(a, a + n, comp); // comparator

    int num = 7;                    /// binary = 111
    int cnt = __builtin_popcount(); // counts set bits in its binary form, counts 1

    long long num1 = 123234234;       /// binary = 111
    int cnt = __builtin_popcountll(); // works only for integers

    string s = "123";

    do
    {
        cout << s << endl;
    } while (next_permutation(s.begin(), s.end())); // checks for true or false

    // DICTIONARY ORDER OF 123
    // 123
    // 132
    // 213
    // 231
    // 312
    // 321
    // find the next permutation to 213

    // next_permutation works for arrays, vectors, list, etc
    // applying next_permutation (a, a+n) will give next permutation.

    int max = *max_element(a, a + n); // find max eement in entire array

    // memeset() - Used to initialize an array to either 0 or -1. Works on any dimentional array
    int arr[5];
    memset(arr, 0, sizeof(arr));  // {0,0,0,0,0}
    memset(arr, -1, sizeof(arr)); // {-1,-1,-1,-1,-1}

    char str[] = "cpp";
    memset(str, 'd', sizeof(str)); // ddd

    int arr2[3][3];
    memset(arr2, -1, sizeof(arr2));
    // -1 -1 -1
    // -1 -1 -1
    // -1 -1 -1

    // Sorting user-defined objects
    static struct Person persons[] = {p1, p2, p3};
    sort(persons, persons + 3, compare_names);
    // This will printout the names in alphabetical order
    for (int i = 0; i < 3; i++)
    {
        cout << persons[i].name << " ";
    }

    // These are various comparator functions
    struct is_older
    {
        bool operator()(struct Person p1, struct Person p2)
        {
            return p1.age > p2.age;
        }
    };
    bool compare_names(struct Person p1, struct Person p2)
    {
        return p1.name < p2.name;
    }
    bool way_to_sort(int i, int j) { return i > j; }

    int x = __gcd(a, b)
}


```


[![](https://img.shields.io/badge/back%20to%20top-%E2%86%A9-blue)](#stl)
  </p>
</details>	  
    

	  

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


	  
	  
	  
Further reading
	  
- https://www.hackerearth.com/practice/notes/standard-template-library/
	  
    
