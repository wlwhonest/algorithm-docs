# 🔗 并查集 Disjoint Set Union

## 📌 模板代码（C++）
```cpp
int fa[N];
int find(int x) {
    return x == fa[x] ? x : fa[x] = find(fa[x]);
}
void unite(int x, int y) {
    fa[find(x)] = find(y);
}
```

## 💡 应用场景
- 判断连通性
- Kruskal最小生成树
