#include <iostream>
#include <vector>
#include <map>
#include <stack>
using namespace std;

void Toposort(char Node, vector<bool>& visited, map<char,vector<char>>& adj, stack<char>& st) {
    visited[Node - 'A'] = true;
    for (auto it : adj[Node]) {
        if (!visited[it - 'A']) {
            Toposort(it, visited, adj, st);
        }
    }
    st.push(Node);
}

int main() {
    int n, e;
    cin >> n >> e;
    
    map<char, vector<char>> adj;
    vector<bool> visited(n, false); // Changed to n from n+1
    
    char u, v;
    for (int i = 0; i < e; i++) {
        cin >> u >> v;
        adj[u].push_back(v);
        // Ensure both directions are added to account for directed graph
    }
    
    stack<char> st;
    for (char i = 'A'; i < 'A' + n; i++) {
        if (!visited[i - 'A']) Toposort(i, visited, adj, st);
    }
    
    while (!st.empty()) {
        cout << st.top() << " ";
        st.pop();
    }
    
    return 0;
}
