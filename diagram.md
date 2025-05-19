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
flowchart LR
    Head[Head] --> Node1
    Node1[Node A] --> Node2[Node B]
    Node2 --> Node3[Node C]
    Node3 --> Node4[Node D]
    Node4 --> Null[null]
    Tail[Tail] --> Node4
    
    Enqueue[Enqueue: O(1)]
    Dequeue[Dequeue: O(1)]
    
    Enqueue -.-> NewNode[New Node E]
    NewNode -.-> Null
    Node4 -.-> NewNode
    Tail -.-> NewNode
    
    Dequeue -.-> Node2
    
    %% Node styling
    classDef node fill:#A1E5AB,stroke:#333,stroke-width:2px,rx:10,ry:10
    classDef pointer fill:#FFD166,stroke:#333,stroke-width:2px
    classDef nullNode fill:#E9E9E9,stroke:#333,stroke-width:2px,rx:10,ry:10
    classDef operation fill:#118AB2,stroke:#333,stroke-width:2px,color:white,rx:5,ry:5
    classDef newNode fill:#FF7B9C,stroke:#333,stroke-width:2px,rx:10,ry:10
    
    class Node1,Node2,Node3,Node4 node
    class Head,Tail pointer
    class Null nullNode
    class Enqueue,Dequeue operation
    class NewNode newNode
```
