# 🧮 二分查找模板 Binary Search

## 🎯 适用场景
当函数在某区间内单调时，适合使用二分查找。

## 📌 模板代码（C++）
```cpp
int binary_search(int l, int r, function<bool(int)> check) {
    while (l < r) {
        int mid = l + (r - l) / 2;
        if (check(mid)) r = mid;
        else l = mid + 1;
    }
    return l;
}
```

## ✅ 示例应用
```cpp
int lower_bound(vector<int>& a, int target) {
    return binary_search(0, a.size(), [&](int mid) {
        return a[mid] >= target;
    });
}
```
