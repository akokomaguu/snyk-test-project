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
graph TD
    A[Time Complexity] --> B["O(1) - Constant"]
    A --> C["O(n) - Linear"]
    A --> D["O(n²) - Quadratic"]
    style B fill:#9f9,stroke:#333
    style C fill:#bbf,stroke:#333
    style D fill:#f9f,stroke:#333
```

```mermaid
flowchart TD
    Data[DATA] -->|input| Hash1[HASH]
    Data -->|input| Hash2[HASH]
    Data -->|input| Hash3[HASH]
    
    Hash1 -->|output| BitArray
    Hash2 -->|output| BitArray
    Hash3 -->|output| BitArray
    
    subgraph BitArray
        B1[1] --- B2[0] --- B3[1] --- B4[1] --- B5[0] --- B6[0] --- B7[0] --- B8[0] --- B9[1]
    end
    
    style Data fill:#9ce79c,stroke:#333,stroke-width:2px
    style Hash1 fill:#a6c4f5,stroke:#333,stroke-width:2px
    style Hash2 fill:#a6c4f5,stroke:#333,stroke-width:2px
    style Hash3 fill:#a6c4f5,stroke:#333,stroke-width:2px
    
    %% Bit Array styling
    style B1 fill:white,stroke:#333,stroke-width:1px
    style B2 fill:white,stroke:#333,stroke-width:1px
    style B3 fill:white,stroke:#333,stroke-width:1px
    style B4 fill:white,stroke:#333,stroke-width:1px
    style B5 fill:white,stroke:#333,stroke-width:1px
    style B6 fill:white,stroke:#333,stroke-width:1px
    style B7 fill:white,stroke:#333,stroke-width:1px
    style B8 fill:white,stroke:#333,stroke-width:1px
    style B9 fill:white,stroke:#333,stroke-width:1px
    
    %% Color the arrows
    linkStyle 0 stroke:#ff0000,stroke-width:2px
    linkStyle 1 stroke:#ff0000,stroke-width:2px
    linkStyle 2 stroke:#ff0000,stroke-width:2px
    linkStyle 3 stroke:#7f00ff,stroke-width:2px
    linkStyle 4 stroke:#7f00ff,stroke-width:2px
    linkStyle 5 stroke:#7f00ff,stroke-width:2px
```
```mermaid
flowchart TD
    Start([Start]) --> Init[Initialize Head/Tail]
    Init --> Op{Operation?}
    
    Op -->|Insert| Insert[Create New Node]
    Insert --> UpdateTail[Update Tail.next]
    UpdateTail --> MoveTail[Move Tail Pointer]
    
    Op -->|Delete| Check{At Head?}
    Check -->|Yes| UpdateHead[Update Head Pointer]
    Check -->|No| FindPrev[Find Previous Node: O(n)]
    FindPrev --> Bypass[Bypass Deleted Node]
    
    UpdateHead & Bypass --> Free[Free Memory]
    MoveTail & Free --> Stop([Stop])
    
    style Start,Stop fill:#4CAF50,stroke:#333
    style Insert fill:#9f9,stroke:#333
    style UpdateHead,UpdateTail fill:#bbf,stroke:#333
    style FindPrev,Bypass fill:#ffcccb,stroke:#333
```
