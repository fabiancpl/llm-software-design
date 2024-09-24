## User Story 1: View Available Products

**Description:** As a customer, I want to see all available products so that I can choose what to buy.

**Acceptance Criteria:**
- The system displays a list of all available products when the customer selects the option to view products.
- Each product listing includes the product name, price, and available quantity.
- The list refreshes to reflect the current inventory levels.


## User Story 2: Purchase Products

**Description:** As a customer, I want to purchase one or more units of a product as long as they are available so that I can buy what I need.

**Acceptance Criteria:**
- The customer can select one or more products and specify the desired quantities.
- The system checks if the requested quantities are available in the inventory.
- If sufficient stock exists, the purchase proceeds successfully.
- If stock is insufficient, the system notifies the customer and prevents the purchase.

## User Story 3: Provide Username During Purchase

**Description:** As a customer, I need to provide my username during purchase so that my purchase can be recorded.

**Acceptance Criteria:**
- During the checkout process, the system prompts the customer to enter a username.
- The username is recorded and associated with the purchase transaction.
- The system accepts any username without requiring prior registration.

## User Story 4: Record Purchase Transactions

**Description:** As a customer, I want my purchase to be recorded so that there is a record of the transaction.

**Acceptance Criteria:**
- Each purchase transaction is saved in the database upon completion.
- Transaction records include the customer's username, product details, quantities purchased, total price, and timestamp.
- The system ensures data integrity and persistence of transaction records.

## User Story 5: Update Inventory After Purchase

**Description:** As a customer, I want the inventory to be updated after my purchase so that stock levels are accurate.

**Acceptance Criteria:**
- Upon successful purchase, the system deducts the purchased quantities from the inventory.
- Updated stock levels are immediately reflected in the product listings.
- The system prevents inventory levels from dropping below zero.

## User Story 6: Manager Login

**Description:** As a manager, I want to log in with my username and password so that I can access management features.

**Acceptance Criteria:**
- The system provides a login prompt for the manager to enter username and password.
- Credentials are authenticated against the pre-existing database records.
- Successful login grants access to management functionalities; failed login displays an error message.

## User Story 7: Check Product Inventory

**Description:** As a manager, I want to check the available units of a product so that I know the stock levels.

**Acceptance Criteria:**
- After logging in, the manager can view a list of all products with their current inventory levels.
- The inventory view includes product names and available quantities.
- The information displayed reflects the most recent stock levels.

## User Story 8: Update Product Inventory

**Description:** As a manager, I want to update the available units of a product so that I can manage inventory.

**Acceptance Criteria:**
- The manager can select a product to update from the inventory list.
- The system allows the manager to input a new quantity for the selected product.
- Updated quantities are saved to the database and reflected in the product listings.
- The system confirms the update with a success message.

## User Story 9: Purchase Without Prior Registration

**Description:** As a customer, I want to make purchases without needing to register in advance so that I can shop easily.

**Acceptance Criteria:**
- The system does not require customers to create an account before purchasing.
- Customers can provide any username during the purchase process.
- The purchase process is streamlined without registration steps.