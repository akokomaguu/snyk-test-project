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
    A[Start Operation] --> B{Type?}
    B -->|Insert| C{Position?}
    B -->|Delete| D{Key or Position?}
    
    %% Insertion Logic
    C -->|Head| E[Create New Node]
    E --> F[Set next = current head]
    F --> G[Update Head Pointer]
    G --> H[End: O(1)]
    
    C -->|Tail| I[Traverse to tail: O(n)]
    I --> J[Set tail.next = New Node]
    J --> K[Update Tail Pointer]
    K --> H
    
    C -->|Middle| L[Traverse to position: O(n)]
    L --> M[Set new.next = current.next]
    M --> N[Set current.next = new]
    N --> H
    
    %% Deletion Logic
    D -->|Key| O[Traverse until key match: O(n)]
    O --> P{Found?}
    P -->|Yes| Q[Set prev.next = current.next]
    P -->|No| R[Throw KeyError]
    Q --> S[Free memory]
    S --> H
    
    D -->|Position| T[Traverse to position: O(n)]
    T --> U{Valid?}
    U -->|Yes| V[Set prev.next = current.next]
    U -->|No| W[Throw IndexError]
    V --> S
    
    %% Common Paths
    H --> Z[Update Size Counter]
    Z --> Y[Return Status]
    
    style H stroke:#4CAF50,stroke-width:2px
    style R,W stroke:#FF5722
    style G,K stroke:#2196F3
```
