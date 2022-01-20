```C++
#include <algorithm>
#include <iostream>
#include <map>
#include <unordered_map>
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

    // UNORDERED MAP
    // does not store in sorted manner, takes O(1), collision might happen

    return 0;
}