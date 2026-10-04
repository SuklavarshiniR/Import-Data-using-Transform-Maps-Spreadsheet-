# Import Data Using Transform Maps (Spreadsheet)

## Project Overview

This project demonstrates how to import employee data from an Excel spreadsheet into ServiceNow using **Import Sets and Transform Maps**. The imported data is transferred from a staging table to a target table through field mappings, with coalesce configuration used to identify matching employee records.

The project also includes reports to organize and visualize employee information by department and location.

## Objectives

- Import employee information from a spreadsheet into ServiceNow.
- Configure an Import Set staging table.
- Create and configure a Transform Map.
- Map source fields to target fields.
- Use coalesce to identify matching employee records.
- Generate reports based on employee data.

## Technologies Used

- ServiceNow Platform
- Import Sets
- Transform Maps
- Excel Spreadsheet
- ServiceNow Tables and Reports

## Project Workflow

```text
Excel Spreadsheet
       |
       v
Employee Import Table
(u_employee_import)
       |
       v
Sample Spreadsheet Import
Transform Map
       |
       v
Field Mapping & Coalesce
       |
       v
Employee Test Table
(u_employee_test)
       |
       v
ServiceNow Reports
```

## Implementation Details

### 1. Source Data

Employee information is provided through an Excel spreadsheet containing fields such as employee ID, email, name, location, and department.

### 2. Import Set Table

The staging table used for importing the spreadsheet data is:

`u_employee_import`

The imported records are temporarily stored in this table before being transformed.

### 3. Transform Map

**Transform Map Name:** Sample Spreadsheet Import Transform Map

The Transform Map transfers data from the Import Set staging table to the target Employee Test table.

### 4. Target Table

The destination table is:

`u_employee_test`

The transformed employee records are stored in this table.

## Field Mapping Configuration

| Source Field | Target Field | Configuration |
|---|---|---|
| Employee ID | Employee ID | Direct mapping |
| Email | Email | Direct mapping |
| Name | Employee Name | Coalesce enabled |
| Location | Location | Direct mapping |
| Department | Department | Direct mapping |

**Coalesce:** Enabled for the Name → Employee Name mapping. This configuration is intended to identify matching records and help avoid duplicate records based on the configured field.

## Reports

The following reports are configured in ServiceNow:

1. **Employees List** – Displays employee records.
2. **Employees by Department** – Organizes employee records by department.
3. **Employees by Location** – Organizes employee records by location.

## Testing and Results

The project includes sample employee records in the target table, with six visible records identified as SB0001–SB0006.

The implementation demonstrates the configured spreadsheet import workflow, field mappings, target table, and employee reports. Formal performance benchmarks and quantitative performance measurements have not been documented.

## Advantages

- Reduces manual data entry.
- Supports structured spreadsheet data imports.
- Provides centralized employee information.
- Allows field-level mapping between source and target tables.
- Supports record matching through coalesce configuration.
- Enables reporting by department and location.

## Limitations

- Source spreadsheet data must follow the expected structure.
- Incorrect field mappings may affect imported records.
- Data quality depends on the source spreadsheet.
- Import accuracy and performance require validation using representative datasets.

## Future Enhancements

- Add data validation before importing records.
- Improve error handling and import failure reporting.
- Implement scheduled imports for recurring spreadsheet updates.
- Expand duplicate detection and data quality checks.
- Add more employee analytics and reporting options.

## Repository

**GitHub:**  
https://github.com/SuklavarshiniR/Import-Data-using-Transform-Maps-Spreadsheet-

## Project Demonstration

**Demo Video:**  
https://drive.google.com/file/d/12aX-QgQPwr1QlJ5Zz6b78giIpiQZ9gCw/view?usp=sharing

## Conclusion

This project demonstrates a structured approach to importing spreadsheet-based employee data into ServiceNow using Import Sets and Transform Maps. It illustrates staging, field mapping, coalesce configuration, target table population, and report creation in a centralized platform.
