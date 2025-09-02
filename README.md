📊 CSV Validator

CSV Validator is a lightweight and efficient tool for validating CSV files against defined rules and formats.
Built with Java, it ensures that datasets used in analytics, ML pipelines, and business applications are clean, consistent, and error-free before processing.
-------------------------------------------------------------------------------------------------------------------------------------------------------
🚀 Features

✔️ Schema Validation – Check if CSV files follow the expected column names and order.
✔️ Data Type Checking – Validate numeric, string, date, and boolean fields.
✔️ Missing Value Detection – Identify null or incomplete fields automatically.
✔️ Range & Pattern Matching – Validate constraints like ranges, regex patterns, and allowed values.
✔️ Error Reporting – Generate detailed logs for invalid rows and columns.
✔️ Lightweight Integration – Can be integrated into Java-based ETL, ML, or backend systems.
-------------------------------------------------------------------------------------------------------------------------------------------------------
🧠 Tech Stack

Language: Java

Build Tool: Maven / Gradle (if applicable)

IDE: IntelliJ IDEA (Project configs in .idea/)

-------------------------------------------------------------------------------------------------------------------------------------------------------
🔧 Setup & Installation

1. Clone the Repository

git clone https://github.com/<your-username>/csv-validator.git
cd csv-validator

2. Open in IntelliJ IDEA or any Java IDE

Import the project as a Java Project
Ensure JDK 8+ is configured

3. Build & Run

If using Maven:
mvn clean install
mvn exec:java -Dexec.mainClass="com.validator.Main"

If running directly:

javac -d out src/**/*.java
java -cp out com.validator.Main

-------------------------------------------------------------------------------------------------------------------------------------------------------
🧪 Usage

Place your CSV file in the data/ folder (or provide a path).

Define validation rules in config.json (example below):

{
  "columns": {
    "id": "int",
    "name": "string",
    "age": "int",
    "email": "regex:^\\S+@\\S+\\.\\S+$"
  },
  "required": ["id", "name", "email"]
}


Run the program – it will print results in the console and generate a report.txt.

-------------------------------------------------------------------------------------------------------------------------------------------------------
📁 Project Structure
csv-validator/
├── src/                  # Java source code
│   └── com/validator     # Core validation logic
├── data/                 # Sample CSV files
├── config.json           # Validation rules
├── out/                  # Compiled output
└── README.md             # Documentation

-------------------------------------------------------------------------------------------------------------------------------------------------------
📌 Known Issues

⚠️ Large CSV files (>1M rows) may require memory optimization.
⚠️ Regex-heavy validations can slow performance.

-------------------------------------------------------------------------------------------------------------------------------------------------------
🤝 Contributing

Contributions are welcome! Please follow these steps:

Fork the repo

Create a feature branch (git checkout -b feature-name)

Commit changes (git commit -m 'Add new validation rule')

Push to your branch (git push origin feature-name)

Open a Pull Request

-------------------------------------------------------------------------------------------------------------------------------------------------------
