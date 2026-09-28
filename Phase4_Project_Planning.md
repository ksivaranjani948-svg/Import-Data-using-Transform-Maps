# Phase 4: Project Planning

## Team Structure
| Member | Role | Responsibility |
|---|---|---|
| Siva Ranjani (Team Lead) | Table Design | Create Employee Test table & fields; overall coordination and GitHub/SkillWallet submission |
| Mari A | Data Import Setup | Create Import Set table + Transform Map, configure field mapping |
| Indhu | Data Integrity | Run Transform, validate records, enable Coalesce, test duplicate handling |
| Subathra | Analytics | Build 3 reports and consolidate into the Dashboard |

## Task Breakdown & Sequencing
Since all technical steps depend on the previous step's output, work was planned sequentially:

| Step | Task | Owner | Depends On |
|---|---|---|---|
| 1 | Prepare sample spreadsheet | Team Lead | - |
| 2 | Create Employee Test table & fields | Team Lead | Step 1 |
| 3 | Create Import Set table | Mari | Step 2 |
| 4 | Create & configure Transform Map | Mari | Step 3 |
| 5 | Run Transform, validate data | Indhu | Step 4 |
| 6 | Enable Coalesce, test duplicate import | Indhu | Step 5 |
| 7 | Build 3 Reports | Subathra | Step 5 |
| 8 | Build Dashboard, add reports | Subathra | Step 7 |

## Milestones (as tracked on SkillWallet)
1. **Milestone 1:** Creation of Spreadsheet and Table
2. **Milestone 2:** Creation of Import Set Table and Transform Map
3. **Milestone 3:** Transform Data & Validate, Enable Coalesce to Avoid Duplicate Records
4. **Milestone 4:** Creation of Reports & Dashboards

## Timeline
| Phase | Target |
|---|---|
| Setup (table, import set, transform map) | Day 1 |
| Validation & Coalesce testing | Day 1-2 |
| Reports & Dashboard | Day 2 |
| Documentation & GitHub upload | Day 2-3 |
| Demo video recording | Day 3 |

## Risk & Mitigation
| Risk | Mitigation |
|---|---|
| Each member has a separate ServiceNow PDI, causing data not to be visible across accounts | Each member independently replicates the base table/import/transform setup on their own instance before doing their specific task |
| Duplicate records on repeated import | Coalesce enabled on Employee ID field |
| Deadline pressure | Followed the official updated deadline (28th September) communicated via faculty |
