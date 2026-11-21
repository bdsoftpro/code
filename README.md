
flowchart TB
    PLATFORM["Nearby Shop Network<br/>E-Commerce Platform"]

    VENDOR["Vendor / Shop Owner"]
    CUSTOMER["Customer"]
    DELIVERY["Delivery Network"]
    ADMIN["Platform Administration"]

    subgraph VENDOR_SIDE["Vendor Business Ecosystem"]
        APP["Vendor Business Management App"]
        LOCAL["Local Business Server"]
        WEBSITE["Personal Online Store"]
        INTEGRATION["Marketplace Integration Module"]
        INVENTORY["Product & Inventory Management"]

        APP --> LOCAL
        APP --> WEBSITE
        APP --> INTEGRATION
        APP --> INVENTORY
    end

    subgraph CUSTOMER_SIDE["Customer Ecosystem"]
        CAPP["Customer Application"]
        LOCATION["Location & Distance Search"]
        DISCOVERY["Nearby Shop & Product Discovery"]
        ORDER["Online Ordering"]
        PICKUP["Physical Store Purchase"]

        CAPP --> LOCATION
        LOCATION --> DISCOVERY
        CAPP --> ORDER
        CAPP --> PICKUP
    end

    VENDOR --> APP
    INTEGRATION <-->|"Authorized Connection"| PLATFORM
    PLATFORM -->|"Live Product Availability & Pricing"| DISCOVERY
    CUSTOMER --> CAPP
    ORDER --> PLATFORM
    PLATFORM --> DELIVERY
    DELIVERY --> CUSTOMER
    PICKUP --> VENDOR
    ADMIN --> PLATFORM
