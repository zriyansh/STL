#include <iostream>
#include <stack>

using namespace std;

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