# Phase 2: Requirement Analysis

## Functional Requirements
| # | Requirement |
|---|-------------|
| FR1 | The system shall accept an Excel spreadsheet containing Employee ID, Name, Email, Department, and Location |
| FR2 | The system shall stage uploaded data in an Import Set table before final insertion |
| FR3 | The system shall map source fields to target fields using a Transform Map |
| FR4 | The system shall create new employee records in the target table upon successful transform |
| FR5 | The system shall avoid creating duplicate employee records on repeated imports (Coalesce) |
| FR6 | The system shall update existing employee records when matching data is re-imported with changes |
| FR7 | The system shall generate a Pie Chart report showing employee count by Department |
| FR8 | The system shall generate a Bar Chart report showing employee count by Location |
| FR9 | The system shall generate a List report showing all employee records with key fields |
| FR10 | The system shall consolidate all 3 reports into a single Dashboard |

## Non-Functional Requirements
- **Usability:** Process should be doable by a beginner ServiceNow admin using only
  out-of-the-box (OOTB) features — no custom scripting required
- **Data Integrity:** No duplicate employee records should exist after multiple imports
  of the same or overlapping data
- **Performance:** Import and transform of ~15-20 records should complete within seconds

## Tools & Platform Requirements
- ServiceNow Personal Developer Instance (PDI)
- Google Sheets (for preparing the source spreadsheet)
- Microsoft Excel format (.xlsx) as the import file type

## Data Requirements
Source spreadsheet must contain these columns:
- Employee ID (unique identifier, e.g., SB-0001)
- Name
- Email
- Department
- Location

## Stakeholders
- **End user (HR/Admin):** uploads spreadsheet, views dashboard
- **ServiceNow Admin (project team):** builds the table, import set, transform map,
  reports and dashboard
