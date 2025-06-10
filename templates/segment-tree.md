# 🌲 线段树 Segment Tree

## 📌 模板代码（C++）
```cpp
struct Node {
    int l, r, sum;
} tr[N * 4];

void build(int u, int l, int r) {
    tr[u] = {l, r};
    if (l == r) return;
    int mid = (l + r) / 2;
    build(u * 2, l, mid);
    build(u * 2 + 1, mid + 1, r);
}
```
