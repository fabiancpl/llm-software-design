## User Story 1: View Available Products

**Description:** As a customer, I want to see all available products so that I can choose what to buy.

**Acceptance Criteria:**
- The system displays a list of all available products when the customer selects the option to view products.
- Each product listing includes the product name, price, and available quantity.
- The product list reflects the current inventory levels by fetching fresh data from the database each time it's requested.

## User Story 2: Purchase Products

**Description:** As a customer, I want to purchase one or more units of a single product by providing my username so that my purchase can be recorded and the inventory is updated.

**Acceptance Criteria:**
- The customer can select a single product from the list of available products.
- The system prompts the customer to specify the desired quantity of that product.
- Before completing the purchase, the system prompts the customer to enter a username.
- The system accepts any username without requiring prior registration.
- The system checks if the requested quantity is available in the inventory.
    - If sufficient stock exists:
        - The purchase proceeds successfully.
        - The system updates the inventory by deducting the purchased quantity.
        - The system records the purchase transaction with the customer's username, product details, quantity purchased, total price, and timestamp.
        - The system displays a confirmation message summarizing the purchase.
    - If stock is insufficient:
        - The system notifies the customer that the requested quantity is not available and prevents the purchase.
- After the transaction (successful or not), the system automatically returns the customer to the list of available products (User Story 1).

## User Story 3: Manager Login

**Description:** As a manager, I want to log in with my username and password so that I can access management features.

**Acceptance Criteria:**
- The system provides a login prompt for the manager to enter username and password.
- Credentials are authenticated against the pre-existing database records.
- Successful login grants access to management functionalities; failed login displays an error message.

## User Story 4: Update Product Inventory

**Description:** As a manager, I want to update the available units of a product so that I can manage inventory.

**Acceptance Criteria:**
- After logging in, the manager can select a product to update from the inventory list.
- The system allows the manager to input a new quantity for the selected product.
- Updated quantities are saved to the database (CSV files) and reflected in the product listings.
- The system confirms the update with a success message.