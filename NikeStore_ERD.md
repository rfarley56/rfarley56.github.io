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

Product table is related to the sale and inventory tables by the productcode. This allows the aggregation of the total sale by the quantity and price of the product. The inventory can be updated by subtracting the quantity sold from the quantityavailable. The customer table is related to the sale by customernumber to track purchased products by the customer
