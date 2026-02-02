# Salesforce Inventory Tracker (LWC + Flow)

## Overview
This project is a lightweight inventory tracking system built on Salesforce using custom objects, record-triggered Flows, and a Lightning Web Component (LWC).

The primary design goal is **data integrity**: inventory quantities are never edited directly. All inventory changes are derived from transaction records, providing a full audit trail and preventing manual manipulation.

---

## Features
- Transaction-based inventory updates (Stock In / Stock Out / Adjustment)
- System-controlled inventory quantities
- Full audit history of inventory movement
- Record-triggered Flow for automation (no Apex required)
- Lightning Web Component for guided transaction entry
- Validation rules to prevent negative inventory
- Formula-driven inventory status (In Stock / Low Stock / Out of Stock)

---

## Data Model

### Inventory Item
Represents the product or item being tracked.

**Key Fields**
- Item Name
- SKU (Unique)
- Category
- Current Quantity (system-controlled)
- Reorder Level
- Status (formula)

---

### Inventory Transaction
Represents a change in inventory.

**Key Fields**
- Inventory Item (Lookup)
- Location (Lookup)
- Transaction Type (Stock In / Stock Out / Adjustment)
- Quantity
- Transaction Date
- Notes

---

### Location
Represents a warehouse or storage location.

**Key Fields**
- Name
- Address
- Manager

---

## Relationships
- Inventory Item → Inventory Transactions (1-to-many)
- Location → Inventory Transactions (1-to-many)

---

## Inventory Logic

Inventory quantities are updated using a **record-triggered Flow** that runs after an Inventory Transaction is created:

- **Stock In** → Adds quantity
- **Stock Out** → Subtracts quantity
- **Adjustment** → Sets quantity directly (admin use)

A validation rule prevents stock-out transactions that exceed the available inventory quantity.

---

## Lightning Web Component

The LWC provides a simple user interface for recording inventory transactions:

- Built using `lightning-record-edit-form`
- Respects Salesforce security and validation
- Delegates all business logic to Flow
- Displays confirmation feedback via toast messages

Users do not have direct access to inventory quantity fields.

---

## Why Flow Instead of Apex?
This MVP intentionally uses Flow to:
- Keep business logic admin-maintainable
- Reduce technical complexity
- Improve visibility and debugging
- Align with Salesforce best practices for transactional automation

Apex can be introduced later if scale or complexity requires it.

---

## Out of Scope (By Design)
- Bulk inventory imports
- Advanced demand forecasting
- Approval processes
- Multi-currency support

These features were intentionally excluded to keep the solution focused and maintainable.

---

## Potential Enhancements
- Apex service to fetch real-time inventory data in LWC
- Low-stock alerts (Email / Slack)
- Inventory dashboards and reports
- Role-based UI behavior
- Mobile-optimized transaction entry

---

## Build Time
- MVP: ~4–6 hours
- Production-ready version: 1–2 days

---

## Purpose
This project demonstrates:
- Salesforce data modeling best practices
- Declarative automation using Flow
- LWC integration without over-engineering
- Thoughtful design decisions aligned with platform strengths
