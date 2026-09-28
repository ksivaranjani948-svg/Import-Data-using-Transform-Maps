# Phase 7: Project Documentation

## Project Summary
**Import Data using Transform Maps (Spreadsheet)** is a ServiceNow micro-project that
demonstrates the end-to-end process of migrating structured employee data from an
external Excel spreadsheet into the ServiceNow platform using **Import Sets** and
**Transform Maps**, with duplicate prevention via **Coalesce**, and business insight
delivery through **Reports** and a **Dashboard**.

## Key ServiceNow Concepts Used
| Concept | Purpose |
|---|---|
| Custom Table | Stores the final, clean employee data |
| Import Set Table | Temporary staging area for raw uploaded data |
| Transform Map | Defines field-level mapping from source to target table |
| Coalesce | Prevents duplicate records; updates existing records instead |
| Reports (Pie/Bar/List) | Visualizes data in different formats |
| Dashboard | Consolidates multiple reports into a single view |

## How to Reproduce This Project
1. Prepare an Excel spreadsheet with columns: Employee ID, Name, Email, Department, Location
2. Create a custom table `Employee Test` (u_employee_test) with matching String fields
3. Use Load Data to create an Import Set table and upload the spreadsheet
4. Create a Transform Map mapping the Import Set fields to the Employee Test fields
5. Run Transform to migrate the data
6. Enable Coalesce on the Employee ID field to prevent duplicates
7. Test by re-uploading modified/duplicate data
8. Build 3 reports (Pie, Bar, List) on the Employee Test table
9. Create a Dashboard and add all 3 reports to it

## Conclusion
This project successfully implemented an automated employee data management solution
using ServiceNow Import Sets and Transform Maps, ensuring accuracy, efficiency, and data
integrity throughout the employee onboarding and update process.

A key enhancement was the use of Coalesce in the Transform Map. By enabling Coalesce on
the Employee ID field, the system intelligently identifies existing employee records during
every import. This prevents duplicate records and ensures that repeated imports update
existing data instead of inserting redundant entries — keeping the employee database
clean, reliable, and consistent, which is critical in real-world enterprise environments.

The project was further extended with Reports and Dashboards to provide meaningful
insights and real-time visibility into employee data and import activity, tracking total
employee records, newly added employees, updated records, and department-wise
distribution — all consolidated into a single centralized Dashboard for administrators
and HR teams.

## References
- ServiceNow official documentation on Import Sets & Transform Maps
- Project reference document and video shared by SmartBridge / Naan Mudhalvan program
