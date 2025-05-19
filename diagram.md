```mermaid
graph LR
    A[Queue FIFO] --> B["Front → A"]
    B --> C["B"]
    C --> D["C ← Rear"]
    style B fill:#f9f,stroke:#333
    style C fill:#bbf,stroke:#333
    style D fill:#9f9,stroke:#333
```

```mermaid
graph TD
    A[Hash Table] --> B["Bucket 0: []"]
    A --> C["Bucket 1: 11"]
    A --> D["Bucket 2: 7, 12"]
    style B fill:#f9f,stroke:#333
    style C fill:#bbf,stroke:#333
    style D fill:#9f9,stroke:#333
```

```mermaid
xychart-beta
    title "Time Complexity"
    x-axis "Input Size (n)" --> 1, 10, 100
    y-axis "Time (ms)" --> 1, 100, 10000
    line "O(1)" --> [(1,1), (10,1), (100,1)]
    line "O(n)" --> [(1,1), (10,10), (100,100)]
    line "O(n²)" --> [(1,1), (10,100), (100,10000)]
```
