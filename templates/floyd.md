# 🔁 Floyd 全源最短路

## 📌 模板代码（C++）
```cpp
for (int k = 1; k <= n; ++k)
    for (int i = 1; i <= n; ++i)
        for (int j = 1; j <= n; ++j)
            g[i][j] = min(g[i][j], g[i][k] + g[k][j]);
```
