# Phase 5: Project Development

This phase covers the actual build steps carried out in the ServiceNow Personal Developer
Instance (PDI).

## Step 1: Prepare the Spreadsheet
- Created a new Google Spreadsheet with columns: Employee ID, Name, Email, Department, Location
- Populated 15 sample employee records (e.g., SB-0001 to SB-0015)
- Downloaded the sheet as `Sample Spreadsheet.xlsx`

## Step 2: Create the Custom Table
- Navigated to **Tables > Create New**
- Label: `Employee Test`, Name: `u_employee_test`
- Added fields via Form Layout: Employee ID, Employee Name, Email, Department, Location
  (all String type)

## Step 3: Create the Import Set Table
- Navigated to **Load Data**
- Label: `Employee Import` (Name auto-populated as `u_employee_import`)
- Uploaded `Sample Spreadsheet.xlsx`, Sheet number 1, Header row 1
- Submitted — received Success message (15 records processed)

## Step 4: Create the Transform Map
- Clicked **Create Transform Map** from the success screen
- Name: `Sample Spreadsheet Import`
- Source Table: Employee Import (auto-populated)
- Target Table: Employee Test
- Used **Auto Map Matching Fields**, then refined mapping using **Mapping Assist**
- Saved, confirming all 5 fields correctly mapped

## Step 5: Run the Transform
- Clicked **Transform**, selected the import set, clicked **Transform** button
- Result: State = Complete, Completion code = Success
- Opened the Employee Test table and confirmed all 15 records were created correctly
- Rearranged columns using Personalized List Columns for readability

## Step 6: Enable Coalesce
- Opened the Transform Map (`Sample Spreadsheet Import`) via **System Import Sets > Transform Maps**
- Under Field Maps, set Coalesce = **true** for the `Employee ID` field
- Saved the form

## Step 7: Test Duplicate Handling
- Re-uploaded a modified version of the spreadsheet with:
  - 2 existing rows changed (email and name updates)
  - 2 brand-new employee rows added
- Ran the Load Data + Transform again
- Result: 2 new records **Inserted**, 2 existing records **Updated** — confirming Coalesce
  worked correctly
- Repeated the exact same upload a second time: result was 0 Inserted, 0 Updated, 4 **Ignored**
  — confirming no duplicate records were created

## Step 8: Build Reports
- **Employees by Department** — Pie chart, grouped by Department, Count aggregation
- **Employees by Location** — Bar chart, grouped by Location, Count aggregation
- **Employee List Report** — List type showing Employee ID, Name, Email, Department, Location

## Step 9: Build Dashboard
- Enabled Admin Override on the `pa_dashboards` ACL to allow dashboard creation
- Created dashboard: **Employee Analytics Dashboard**
- Added all 3 reports to the dashboard via the Share > Add to Dashboard option
- Verified all 3 widgets render correctly side-by-side on the dashboard
