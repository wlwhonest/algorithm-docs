# 🔍 KMP 字符串匹配

## 📌 模板代码（C++）
```cpp
void build_next(string &pattern, vector<int> &nxt) {
    int j = 0;
    nxt[0] = 0;
    for (int i = 1; i < pattern.size(); ++i) {
        while (j && pattern[i] != pattern[j]) j = nxt[j - 1];
        if (pattern[i] == pattern[j]) ++j;
        nxt[i] = j;
    }
}
```
