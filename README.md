Salesforce Inventory Tracker (Starter Project)

A beginner-friendly Salesforce project for tracking inventory transactions using Custom Objects, Apex, and Visualforce.

This project is designed as a learning tool for understanding how data flows through Salesforce—from UI to controller to database—while handling validation and business logic.
<img width="536" height="424" alt="inventoryTracker" src="https://github.com/user-attachments/assets/08bc682c-1a7e-4189-9e0d-b82d90bd1fa2" />


📦 Features

Track inventory quantities in real time

Log stock movements (in, out, adjustments)

Validate transactions before saving

Display current inventory levels in a table

🧱 Architecture Overview
Custom Objects

Inventory_Item__c

Stores inventory items

Tracks current quantity on hand

Inventory_Transaction__c

Records inventory changes

Supports stock in, stock out, and adjustments

Visualforce Page

Simple transaction entry form

Picklists for:

Inventory Item

Transaction Type

Quantity input field

Displays:

Error messages

Current inventory table with quantities

Apex Controller

Saves inventory transactions

Updates item quantities automatically

Validates:

Required fields

Sufficient stock for stock-out transactions

Returns user-friendly error messages
