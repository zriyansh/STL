```C++
#include <iostream>
#include <set>

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