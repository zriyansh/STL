#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

bool f(int x, int y)
{
    return x > y;
}
// comparator funtion, used to sort in descreasing order if returns x>y.

int32_t main()
{
    // We use int32_t  for faster compilation and also because main() should always return value accoring to 32bit system, even 64bit system use 32bit int.
    ios_base::sync_with_stdio(0);
    // the first line turns off buffer synchronization between the cin stream and C-style stdio tools (like scanf or gets) — so cin works faster, but you can't use it simultaneously with stdio tools.
    cin.tie(NULL);
    // The second line unties cin from cout — by default the cout buffer flushes each time when you read something from cin.

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