# 🛣️ Dijkstra 最短路算法

## 📌 模板代码（C++）
```cpp
priority_queue<PII, vector<PII>, greater<>> q;
vector<PII> g[N];
int dist[N];

void dijkstra(int s) {
    memset(dist, 0x3f, sizeof dist);
    dist[s] = 0;
    q.push({0, s});
    while (q.size()) {
        auto [d, u] = q.top(); q.pop();
        if (d > dist[u]) continue;
        for (auto [v, w] : g[u]) {
            if (dist[v] > d + w) {
                dist[v] = d + w;
                q.push({dist[v], v});
            }
        }
    }
}
```
