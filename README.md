# gift-store
Here is a clean, professional **README.md** file for your project. I have integrated your name as requested and structured the content to be clear for evaluators or fellow developers.

---

# Gift Store Management System

A robust Python-based management system for a digital gift store, utilizing **MySQL** for persistent data storage. The system features a tiered access model for **Customers**, **Vendors**, and **Administrators**, alongside automated security triggers for data integrity.

## ## Project Overview

The Gift Store Management System facilitates the end-to-end process of browsing, purchasing, and managing products. It focuses on secure user authentication, real-time wallet management, and automated account moderation through SQL triggers.

## ## Core Features

### ### For Customers
* **Account Management:** Secure signup/login with profile and wallet management.
* **Shopping Experience:** Browse products with advanced filters (Price, Rating, Name, Refundability).
* **Cart System:** Add, view, and remove items from a personal cart before checkout.
* **Transactions:** Buy items using a digital wallet with automated balance checks.

### ### For Vendors & Admins
* **Inventory Control:** Vendors can add and manage new products.
* **Order Tracking:** View and monitor customer orders and history.
* **System Security:** Automated banning mechanisms for invalid data or suspicious activity.

## ## Database Architecture & Triggers

The system uses advanced **SQL Triggers** to handle business logic and security at the database level:

1.  **Email Validation Trigger (AFTER INSERT ON person):** * Automatically validates email formats.
    * If an invalid email (missing `@`) is inserted more than three times, the associated customer account is flagged and banned.
2.  **Anti-Fraud/Balance Trigger:**
    * Monitors "insufficient balance" attempts during checkout.
    * If a user attempts to purchase with insufficient funds more than 3 times, the account is temporarily locked in the `LockedUsers` table for 30 seconds to prevent spam/brute-force transactions.



## ## Technical Stack

* **Language:** Python 3.x
* **Database:** MySQL
* **Libraries:** * `mysql.connector` (Database connectivity)
    * `datetime` & `time` (Timestamping and ban durations)

## ## Setup Instructions

1.  **Database Setup:**
    * Ensure MySQL is installed and running.
    * Create a database named `GIFTSTORE`.
    * Execute the provided SQL schema scripts to create tables and initialize triggers.

2.  **Configuration:**
    * Update the database credentials (host, user, password) in the Python script's connection section.

3.  **Run the Application:**
    ```bash
    python main.py
    ```

## ## Contributors

This project was developed by:

* **Md Ashif**

* **Sarthak Singh** (2022457)

*All members contributed equally to the design, implementation, and testing of this system.*