📊 CSV Validator

CSV Validator is a lightweight yet powerful Java-based tool designed to validate CSV (Comma-Separated Values) files against defined rules, formats, and schemas. In today’s world of data-driven decision-making, organizations rely on massive volumes of data for analytics, machine learning pipelines, and enterprise business applications. However, the quality of the data determines the quality of the insights.

Incorrect or inconsistent data can lead to wrong business conclusions, failed ML models, and significant operational inefficiencies. The CSV Validator project directly addresses this challenge by providing a robust, extensible, and efficient validation framework to ensure data cleanliness, integrity, and readiness for downstream processing.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
🌍 Why CSV Validation Matters?

CSV is one of the most widely used formats for data exchange and storage. From exporting reports from ERP systems to preparing training datasets for ML models, CSV files play a critical role. However, real-world CSV files are rarely perfect.

Typical challenges include:

❌ Missing headers or inconsistent column names

❌ Incorrect data types (e.g., "Age" field containing text)

❌ Missing or null values in mandatory fields

❌ Values outside expected ranges (e.g., age < 0, salary > 1M)

❌ Invalid email formats or phone numbers

❌ Data duplication across rows

❌ Encoding issues or inconsistent delimiters

Without validation, these issues can propagate errors downstream, leading to bad analytics, biased ML models, and incorrect financial or operational decisions.

CSV Validator ensures that:

Your CSV files adhere to schema definitions.

Data is type-safe and format-consistent.

Missing, invalid, or duplicate records are flagged early.

Detailed error logs are generated for corrective action.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🚀 Features

The CSV Validator includes multiple layers of validation to handle complex use cases:

✔️ Schema Validation

Ensures that the CSV file contains the expected column names, order, and structure.

Detects missing headers, additional unexpected columns, or incorrect ordering.

Example:
Expected schema = ["id", "name", "age", "email"]
Input schema = ["name", "id", "age", "email", "extra"] → Error flagged

✔️ Data Type Checking

Validates that column values conform to defined types (e.g., integers, strings, dates, booleans).

Prevents invalid parsing during data ingestion.

Example:

"age": "int"


If CSV contains age = "twenty", it raises an error.

✔️ Missing Value Detection

Identifies empty or null values in mandatory fields.

Configurable rules to allow/disallow missing data.

Example:

If email is required, rows without email are flagged.

✔️ Range & Pattern Matching

Enforces numeric ranges (e.g., age must be between 18–65).

Uses regex for string patterns (e.g., valid email addresses, phone numbers).

Example:

"email": "regex:^\\S+@\\S+\\.\\S+$"


Only accepts correctly formatted emails.

✔️ Error Reporting

Generates detailed reports including:

Line numbers

Column name

Type of error

Suggested fix (if applicable)

Outputs errors into both console logs and a report.txt file for documentation.

✔️ Lightweight Integration

Can be easily embedded into Java-based ETL pipelines, ML workflows, or enterprise backends.

Works with Maven/Gradle for seamless project integration.

Scales to handle large datasets with minimal configuration.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🧠 Tech Stack

Language: Java (JDK 8+)

Build Tool: Maven / Gradle for dependency management

IDE: IntelliJ IDEA (with project configs in .idea/)

Libraries: Core Java I/O, JSON parser for config rules

OS Support: Cross-platform (Windows, Linux, macOS)

Why Java?

Strong support for file handling and large datasets.

Excellent performance for enterprise-level applications.

Ecosystem maturity for building scalable ETL components.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🔧 Setup & Installation

1. Clone the Repository
git clone https://github.com/<your-username>/csv-validator.git
cd csv-validator

2. Open in IntelliJ IDEA or Java IDE

Import project as a Java Project.

Configure JDK 8+.

3. Build & Run
If using Maven:
mvn clean install
mvn exec:java -Dexec.mainClass="com.validator.Main"

If running directly:
javac -d out src/**/*.java
java -cp out com.validator.Main

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🧪 Usage

Place CSV file inside data/ folder.

Define validation rules in config.json.

Example:

{
  "columns": {
    "id": "int",
    "name": "string",
    "age": "int",
    "email": "regex:^\\S+@\\S+\\.\\S+$"
  },
  "required": ["id", "name", "email"],
  "ranges": {
    "age": { "min": 18, "max": 65 }
  }
}


Run the Validator

java -cp out com.validator.Main

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Output

Console shows summary of valid vs invalid rows.

report.txt logs detailed issues for debugging.

📁 Project Structure
csv-validator/
├── src/                  # Java source code
│   └── com/validator     # Core validation logic
├── data/                 # Sample CSV files
├── config.json           # Validation rules
├── out/                  # Compiled output
└── README.md             # Documentation

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

📊 Example Walkthrough

Input CSV (data/sample.csv):
id,name,age,email
1,Alice,25,alice@example.com
2,Bob,17,bob@com
3,Charlie,,charlie@example.com
4,David,40,davidexample.com

Config Rules:

age must be int between 18–65.

email must match regex.

name cannot be missing.

Output Report:
Line 2: age = 17 (Out of range)
Line 2: email = bob@com (Invalid email format)
Line 3: age = NULL (Missing value)
Line 4: email = davidexample.com (Invalid email format)

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

📌 Known Issues

⚠️ Large CSVs (>1M rows) may require memory optimization.

⚠️ Regex-heavy validations can slow performance.

⚠️ UTF-8 vs ANSI encoding inconsistencies can cause parsing errors.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🎯 Use Cases

✅ Preprocessing datasets for ML pipelines

✅ Ensuring clean data ingestion for data warehouses

✅ Validating CSV exports from ERP/CRM tools

✅ Automating QA checks for ETL jobs

✅ Cleaning financial/transactional CSV data before audits

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🚀 Future Enhancements

Add parallel processing for large datasets.

Support other formats like TSV/JSON.

Build GUI version for non-technical users.

Add data deduplication checks.

Integrate with cloud pipelines (AWS S3, GCP BigQuery).

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🤝 Contributing

Fork the repo.

Create a branch:

git checkout -b feature-name

Commit changes:

git commit -m "Added new feature"

Push & create a Pull Request.
<img width="451" height="682" alt="image" src="https://github.com/user-attachments/assets/f0665cbe-45b5-4c49-b0e3-c04097b49d07" />
