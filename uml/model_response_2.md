@startuml
title Class Diagram for Command-Line Online Store (Including Presentation Layer)

' Define classes for models
class Product {
    - int productId
    - String productName
    - Decimal price
    - int availableQuantity
    --
    + int getProductId()
    + void setProductId(int)
    + String getProductName()
    + void setProductName(String)
    + Decimal getPrice()
    + void setPrice(Decimal)
    + int getAvailableQuantity()
    + void setAvailableQuantity(int)
}

class Purchase {
    - int purchaseId
    - String username
    - int productId
    - int quantityPurchased
    - Decimal totalPrice
    - DateTime purchaseTimestamp
    --
    + int getPurchaseId()
    + void setPurchaseId(int)
    + String getUsername()
    + void setUsername(String)
    + int getProductId()
    + void setProductId(int)
    + int getQuantityPurchased()
    + void setQuantityPurchased(int)
    + Decimal getTotalPrice()
    + void setTotalPrice(Decimal)
    + DateTime getPurchaseTimestamp()
    + void setPurchaseTimestamp(DateTime)
}

class Manager {
    - int managerId
    - String username
    - String password
    --
    + int getManagerId()
    + void setManagerId(int)
    + String getUsername()
    + void setUsername(String)
    + String getPassword()
    + void setPassword(String)
}

' Define service classes
class CustomerService {
    + void purchaseProduct(String username, int productId, int quantity)
    + List<Product> viewAvailableProducts()
}

class ManagerService {
    + void updateInventory(int productId, int newQuantity)
}

class AuthenticationService {
    + boolean authenticateManager(String username, String password)
}

' Define repository classes
class ProductRepository {
    + List<Product> findAll()
    + Product findById(int productId)
    + void update(Product product)
}

class PurchaseRepository {
    + void save(Purchase purchase)
}

class ManagerRepository {
    + Manager findByUsername(String username)
}

' Define presentation layer classes
class MainMenu {
    + void displayMenu()
}

class CustomerInterface {
    + void viewProducts()
    + void purchaseProduct()
}

class ManagerInterface {
    + void login()
    + void updateInventory()
}

' Define relationships

' Presentation Layer interactions
MainMenu --> CustomerInterface : directs to
MainMenu --> ManagerInterface : directs to

CustomerInterface --> CustomerService : uses
ManagerInterface --> ManagerService : uses
ManagerInterface --> AuthenticationService : uses

' Service Layer interactions
CustomerService --> ProductRepository : uses
CustomerService --> PurchaseRepository : uses

ManagerService --> ProductRepository : uses

AuthenticationService --> ManagerRepository : uses

' Repository interactions with models
ProductRepository ..> Product
PurchaseRepository ..> Purchase
ManagerRepository ..> Manager

' Associations with models
CustomerService ..> Product
CustomerService ..> Purchase
ManagerService ..> Product
AuthenticationService ..> Manager

' Associations between Presentation Layer and Models (if any)
CustomerInterface ..> Product
ManagerInterface ..> Product

@enduml
