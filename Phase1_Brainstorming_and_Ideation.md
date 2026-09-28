# Phase 1: Brainstorming & Ideation

## Project Title
**Import Data using Transform Maps (Spreadsheet)**

## Problem Statement
Organizations frequently receive bulk employee or business data in external formats such as
Excel spreadsheets. Manually entering this data into an enterprise system like ServiceNow is
slow, error-prone, and impossible to scale for large datasets. There is a need for an automated,
repeatable process to bring structured spreadsheet data into ServiceNow accurately.

## Idea
Use ServiceNow's built-in **Import Sets** and **Transform Maps** to build a pipeline that:
- Accepts an Excel spreadsheet of employee records as input
- Stages the raw data temporarily in an Import Set table
- Maps and transforms the staged data into a proper target table (Employee Test)
- Prevents duplicate records on repeated imports using **Coalesce**
- Visualizes the imported data through **Reports** and a **Dashboard**

## Why This Approach
- Import Sets + Transform Maps is the standard, industry-recommended ServiceNow method
  for bulk data migration (used in real HR onboarding, CMDB imports, etc.)
- Coalesce logic mirrors real-world scenarios where the same source file may be
  re-uploaded with updated values (e.g., an employee's changed email or department)
- Reports and Dashboards convert raw imported data into actionable business insight,
  extending the project beyond simple data loading into data analytics

## Expected Outcome
A working ServiceNow instance where:
1. A custom "Employee Test" table holds clean, de-duplicated employee data
2. Any new spreadsheet upload automatically inserts new employees and updates
   existing ones without creating duplicates
3. An "Employee Analytics Dashboard" gives a live visual summary (by Department,
   by Location, and a full employee list) for quick decision-making

## Team Brainstorming Notes
- Discussed using CSV vs Excel — chose Excel (.xlsx) since it's the most common
  real-world format HR teams use
- Discussed which field should be the coalesce key — chose **Employee ID** since
  it is the unique identifier for each employee
- Decided to build 3 report types (Pie, Bar, List) to cover different ways of
  viewing the same underlying data
