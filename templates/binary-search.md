# 🔍 模板名称：二分查找（Binary Search）

---

## 📌 适用场景

当某个函数在给定区间内满足 **单调性（递增或递减）** 时，可以使用二分查找在该区间内高效地定位某个值。

---

## 🧠 思维总结

| 类型         | 条件                                  | 返回值         |
|--------------|---------------------------------------|----------------|
| 最小可行值   | `check(mid)` 为 True 时移动右边界     | 最左满足条件值 |
| 最大不可行值 | `check(mid)` 为 False 时移动左边界    | 最右不满足值   |

- 时间复杂度：`O(logN)`
- 二分查找必须满足：目标函数在搜索区间内是单调的
- 使用场景：上/下界查找、最大值最小化、最小值最大化

---

## 💻 模板代码（C++）

```cpp
// 二分查找框架：找最小满足 check(mid) 的值
int binary_search(int l, int r, function<bool(int)> check) {
    while (l < r) {
        int mid = l + (r - l) / 2;
        if (check(mid))
            r = mid;
        else
            l = mid + 1;
    }
    return l;
}
```

---

## 🧪 示例：查找数组中第一个 ≥ target 的位置

```cpp
int lower_bound(vector<int>& a, int target) {
    return binary_search(0, a.size(), [&](int mid) {
        return a[mid] >= target;
    });
}
```

---

## 🧾 注意事项

> [!TIP]
> ✅ 检查搜索区间是否闭合（`[l, r)` 或 `[l, r]`）

> [!WARNING]
> ⚠️ 如果 mid 计算方式或边界更新错误，可能导致死循环！

---

## 📚 拓展阅读

- [LeetCode 704. 二分查找](https://leetcode.cn/problems/binary-search/)
- [浅谈二分查找的四种写法](https://www.acwing.com/blog/content/73/)
