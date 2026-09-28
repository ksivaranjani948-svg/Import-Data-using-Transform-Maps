# Phase 6: Project Testing

## Test Cases

| # | Test Case | Steps | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|
| TC1 | Initial data import | Upload Sample Spreadsheet.xlsx and run Transform | All 15 records created in Employee Test table | 15 records created | ✅ Pass |
| TC2 | Field mapping accuracy | Compare source spreadsheet vs Employee Test table | All 5 fields (ID, Name, Email, Dept, Location) match | Fields matched correctly | ✅ Pass |
| TC3 | Coalesce - new records | Re-upload sheet with 2 new employee rows | New rows inserted only, no duplicates of old data | 2 records inserted | ✅ Pass |
| TC4 | Coalesce - updated records | Re-upload sheet with 2 existing rows modified (name/email changed) | Existing records updated in place, not duplicated | 2 records updated | ✅ Pass |
| TC5 | Coalesce - exact re-import | Re-upload the exact same modified sheet again | 0 inserted, 0 updated, all records ignored | 4 records ignored | ✅ Pass |
| TC6 | Pie chart report | Open Employees by Department report | Chart correctly shows employee count grouped by department | Verified visually | ✅ Pass |
| TC7 | Bar chart report | Open Employees by Location report | Chart correctly shows employee count grouped by location | Verified visually | ✅ Pass |
| TC8 | List report | Open Employee List Report | All employee records visible with correct columns | Verified, 17 records listed | ✅ Pass |
| TC9 | Dashboard integration | Open Employee Analytics Dashboard | All 3 reports visible together on one dashboard | Verified all 3 widgets present | ✅ Pass |
| TC10 | Access restriction | Use Share option to restrict dashboard | Only specified users/groups/roles can view | Restriction option confirmed available | ✅ Pass |

## Summary
All 10 test cases passed. The Coalesce mechanism was specifically validated across three
successive import runs (initial load, modified re-upload, identical re-upload) to confirm
that duplicate prevention and update-in-place logic both function as intended.

## Known Limitations
- Data types are all String; no field-level validation (e.g., email format) is enforced
- Coalesce is only enabled on Employee ID; a real production setup might combine
  multiple fields as a composite key
