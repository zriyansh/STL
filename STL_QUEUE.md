```C++
#include <iostream>
#include <queue>

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
