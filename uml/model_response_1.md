@startuml
skinparam componentStyle rectangle

title Component Diagram for Command-Line Online Store

' Define components in Presentation Layer
package "Presentation Layer" {
    [MainMenu] <<UI>>
    [CustomerInterface] <<UI>>
    [ManagerInterface] <<UI>>
}

' Define components in Application Layer
package "Application Layer" {
    [CustomerService] <<BusinessLogic>>
    [ManagerService] <<BusinessLogic>>
    [AuthenticationService] <<BusinessLogic>>
}

' Define components in Data Access Layer
package "Data Access Layer" {
    [ProductRepository] <<Repository>>
    [PurchaseRepository] <<Repository>>
    [ManagerRepository] <<Repository>>
}

' Define Data Storage
node "Data Storage (CSV Files)" {
    [Products.csv] <<CSV>>
    [Purchases.csv] <<CSV>>
    [Managers.csv] <<CSV>>
}

' Define dependencies between components
[MainMenu] --> [CustomerInterface]
[MainMenu] --> [ManagerInterface]

[CustomerInterface] --> [CustomerService]
[ManagerInterface] --> [AuthenticationService]
[ManagerInterface] --> [ManagerService]

[CustomerService] --> [ProductRepository]
[CustomerService] --> [PurchaseRepository]

[ManagerService] --> [ProductRepository]

[AuthenticationService] --> [ManagerRepository]

[ProductRepository] --> [Products.csv]
[PurchaseRepository] --> [Purchases.csv]
[ManagerRepository] --> [Managers.csv]
@enduml
