Salesforce Inventory Tracker (Starter Project)
Overview

This is a starter Salesforce project to track inventory transactions. It uses:

Custom Objects:

Inventory_Item__c — holds items and their current quantity

Inventory_Transaction__c — logs stock in, stock out, and adjustments

Visualforce Page:

A simple form to record transactions

Picklists for selecting Inventory Items and Transaction Type

Quantity input

Apex Controller:

Handles saving transactions

Updates inventory quantities

Validates inputs and displays errors

This project is intended as a learning tool for Apex, Visualforce, and custom objects in Salesforce.

Setup Instructions

Clone this repository to your Salesforce project folder.

Deploy the Custom Objects:

Inventory_Item__c

Inventory_Transaction__c

Deploy Apex Controller: InventoryController

Deploy Visualforce Page: InventoryTransactionPage

Add Inventory Items:

Go to Setup → Object Manager → Inventory Item → Inventory Items → New

Add a few items with names and starting quantities

Access the page:

Navigate to the Visualforce page in your org to test transactions

How It Works

Select an Inventory Item

Choose a Transaction Type: Stock In, Stock Out, Adjustment

Enter a Quantity

Click Save Transaction

Inventory quantity updates automatically

Errors appear if inputs are missing or stock is insufficient

The page also displays a table of current inventory items and their quantities.
