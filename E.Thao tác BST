#include <bits/stdc++.h>
#define inp "test"
#define ll long long
#define pb push_back
#define all(x) x.begin(), x.end()
#define foru(i, a, b) for (int i = a; i <= b; ++i)
#define ford(i, a, b) for (int i = a; i >= ; --i)

using namespace std;

const ll oo = 0x3f3f3f3f3f3f3f3f;
const ll MOD = 1e9 + 7;
const int maxn = 1e3 + 10;

void fio(){
    ios_base::sync_with_stdio(false);
    cin.tie(nullptr);
}

void read(){
    if (fopen(inp".inp", "r")){
        freopen(inp".inp", "r", stdin);
        freopen(inp".out", "w", stdout);
    }
}

struct Node{
    int data;
    Node* left;
    Node* right;
};

Node* createNode(int val){
    return new Node{val, nullptr, nullptr};
}

void preorder(Node* root) {
    if (root == nullptr) return;
    cout << root->data << " ";
    preorder(root->left);
    preorder(root->right);
}

Node* ins(Node* root, int val){
    if (root == nullptr) return createNode(val);
    if (val < root->data) root->left = ins(root->left, val);
    else if (val > root->data) root->right = ins(root->right, val);
    return root;
}

Node* minNode(Node* root) {
    while (root != nullptr && root->left != nullptr) root = root->left;
    return root;
}

Node* del(Node* root, int val){
    if (root == nullptr) return createNode(val);
    if (val < root->data) root->left = del(root->left, val);
    else if (val > root->data) root->right = del(root->right, val);
    else{
        if (root->left == nullptr){
            Node* next = root->right;
            delete root; return next;
        }
        if (root->right == nullptr){
            Node* next = root->left;
            delete root; return next;
        }
        Node* successor = minNode(root->right);
        root->data = successor->data;
        root->right = del(root->right, successor->data);
    }
    return root;
}

int q;
Node* root = nullptr;

void sol(){
    cin >> q;
    foru(i, 1, q){
        string type; int x;
        cin >> type >> x;
        if (type == "ins"){
            root = ins(root, x);
        } else {
            root = del(root, x);
        }
        cout << "Query #" << i << ": ";
        preorder(root);
        cout << "\n";
    }
}

signed main(){
    fio();
    read();
    int test = 1;
    //cin >> test;
    while (test--){
        sol();
        cout << "\n";
    }
    return 0;
}   
