```mermaid 
erDiagram
    PRODUCT ||--|{ SALE : prodcutCode
        PRODUCT {
        string productCode PK
        float pricePerUnit
        string make
        string model  
    }
    INVENTORY ||--o{PRODUCT : prodcutCode
    INVENTORY { 
        string productCode FK
        float quantityAvaiable
    } 
    CUSTOMER ||--o{ SALE : custNumber
    CUSTOMER {
        string name
        string custNumber PK
    }
    SALE ||--o{ INVENTORY : productCode
    SALE {
        int orderNumber PK
        string custNumber FK
        string productCode FK
        int quantity
        float pricePerUnit
        float totalPrice
    }
```
