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
    Start([Start]) --> Init[Head=null, Tail=null]
    Init --> Op{Insert or Delete?}

    Op -->|Insert| Create[Create New Node]
    Create --> Update[Update Tail.next]
    Update --> Move[Tail = New Node]

    Op -->|Delete| Check{Head == null?}
    Check -->|Yes| Error[Underflow Error]
    Check -->|No| Remove[Remove Head Node]
    Remove --> Free[Free Memory]

    Move & Free --> Stop([Stop])

    style Start,Stop fill:#4CAF50
    style Create,Update fill:#E1F5FE
    style Remove,Free fill:#FFEBEE
```   

```mermaid
graph TD
    subgraph "Array Implementation of Queue"
        subgraph State1["Initial Array"]
            A1[1] --- A2[2] --- A3[3] --- A4[4] --- A5[5]
        end
        
        subgraph State2["After Enqueue"]
            B1[1] --- B2[2] --- B3[3] --- B4[4] --- B5[5] --- B6[E]
            BFront["Front"] -.-> B1
            BRear["Rear"] -.-> B6
        end
        
        subgraph State3["After Dequeue"]
            C0[ ] --- C2[2] --- C3[3] --- C4[4] --- C5[5] --- C6[E]
            CFront["Front"] -.-> C2
            CRear["Rear"] -.-> C6
        end
        
        subgraph State4["Final Queue Elements"]
            D1[2] --- D2[3] --- D3[4] --- D4[5] --- D5[E]
        end
    end
    
    State1 --> State2
    State2 --> State3
    State3 --> State4
    
    %% Styling
    classDef filled fill:#1A5E8E,color:white,stroke:#333,stroke-width:2px,rx:5,ry:5
    classDef empty fill:#88BDBC,color:white,stroke:#333,stroke-width:1px,rx:5,ry:5
    classDef pointer fill:none,stroke:none
    
    class A1,A2,A3,A4,A5,B1,B2,B3,B4,B5,B6,C2,C3,C4,C5,C6,D1,D2,D3,D4,D5 filled
    class C0 empty
    class BFront,BRear,CFront,CRear pointer
```  

