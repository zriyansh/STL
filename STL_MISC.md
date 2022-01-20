```C++
#include <iostream>

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