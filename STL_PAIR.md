#include <iostream>
#include <vector>

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