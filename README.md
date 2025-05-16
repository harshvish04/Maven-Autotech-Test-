# Maven-Autotech-Test-
# Odoo Custom Module Submission - Test Paper

**Candidate:** Harsh Vishwakarma  
**Date:** 16-05-2025  
**Odoo Version:** 18  
**Python Version:** 3.10  

---

## Overview

This repository contains my submission for the Odoo customization test paper. The test includes multiple sections covering module creation, constraints, relational features, inventory and sale order customizations, and report modifications.

Below is a breakdown of what I implemented for each section.

---

## Section A: Module Creation

- Created a custom module named `employee_test_module`.
- Implemented the following views on the model `employee.record`:
  - **Tree View**: Showing all basic fields.
  - **Kanban View**: Custom kanban card displaying selected fields.
  - **Form View**: Contains all field types, including Char, Text, Integer, Float, Boolean, Date, Datetime, Selection, Binary, Html, Many2one, Many2many, and One2many.
- Implemented field behavior:
  - Used `@api.onchange` on one field to dynamically update another.
  - Used `@api.depends` on a computed field to automatically calculate its value based on other fields.

---

## Section B: Constraints

- Added an **SQL constraint** to enforce uniqueness (or a check) on a specific field at the database level.
- Added a **Python constraint** (`@api.constrains`) to validate business logic, e.g., ensuring a date field is not set in the future.

---

## Section C: Relational Features

- Extended the existing `res.country` model by adding a Many2one or Many2many relation field inside the custom model (`employee.record`).
- Added a **header button** in the form view that populates multiple fields with predefined static values on click, demonstrating business logic and UI interactivity.

---

## Section D: Inventory Customization

- Customized the Inventory module by adding a custom field named `custom_batch_note` to the **Detailed Operations** section within the Batch Transfer form (`stock.picking.batch` model).
- This enhances batch transfers by allowing users to enter additional notes specific to each batch.

---

## Section E: Sale Order View Customization

- Customized the **Sale Order Kanban View** by using XPath to insert a custom field `client_order_ref` between the Sale Order name and date.
- This modification improves order visualization and referencing in Kanban view.

---

## Section F: Report Customization

- Modified the **Picking Operation Report** used in delivery orders.
- Adjusted report logic and XML so that product names do not repeat for the same product across multiple lines.
- Ensured all other fields (quantity, lot/serial numbers, etc.) remain visible for each operation line.
- This makes reports cleaner and easier to read.

---

## Installation & Testing Instructions

1. Place the `employee_test_module` folder inside your Odoo addons directory.  
2. Restart your Odoo server.  
3. Update the Apps list and install the `employee_test_module`.  
4. Test each functionality:
   - **Section A-C:** Check employee records with all fields, form button functionality, and constraints.  
   - **Section D:** Go to Inventory > Batch Transfers and see the added custom note field.  
   - **Section E:** Go to Sales > Orders, switch to Kanban view, and verify the new field between order name and date.  
   - **Section F:** Generate a delivery picking report to confirm product names are grouped without repetition.

---

## File Structure

