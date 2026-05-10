# ⚙️ Smart-Disk-Optimiser: Intelligent Duplicate File Remover

# 📌 Project Overview

This project is a high-performance Python-based automation utility designed to optimize disk space by identifying and removing duplicate files. Unlike simple name-based detection, this tool utilizes MD5 cryptographic hashing to ensure data integrity, identifying duplicates based on actual file content regardless of their filenames.

# 🛠 Tech Stack & Environment

Language: Python 3.x

Standard Libraries: hashlib (Cryptographic Hashing), os (File System Operations)

Platform: Cross-platform (Linux, Windows, macOS)

Concepts: MD5 Checksum Calculation, Recursive Directory Traversal, Dictionary-based Grouping

# 📦 Dependencies & Requirements

This utility uses only Python standard libraries to ensure zero-dependency deployment:

Python 3.6+: Required for modern dictionary implementations.

Storage Access: Read/Write permissions for the target scanning directory.

# 🧠 Core Logic

The system architecture follows a three-stage "Scan-Verify-Optimise" workflow:

Content-Based Fingerprinting:

Binary Processing: Files are opened in rb (read-binary) mode to handle all file types (Images, PDFs, Videos).

Chunked Hashing: To prevent memory overflow with large files, the utility reads data in 1KB chunks while updating the MD5 hash object.

Recursive Search & Grouping:

Uses os.walk to traverse nested subdirectories.

Employs a Dictionary (Hash Map) where the Key is the unique MD5 checksum and the Value is a list of absolute paths sharing that content.

Automated Optimization:

The tool filters the dictionary for keys with more than one path.

Preservation Policy: It preserves the first discovered instance (Original) and safely removes all subsequent entries using os.remove().

# 🚀 Execution Steps

1. Setup

Clone the repository and ensure you have Python installed:

git clone [https://github.com/your-username/smart-disk-optimiser.git](https://github.com/your-username/smart-disk-optimiser.git)
cd smart-disk-optimiser


2. Running the Utility

The script can be executed by passing the target directory as an argument (or it defaults to the project root):

# Usage: python optimiser.py <Target_Directory_Path>
python optimiser.py "C:/Users/Documents/Data"


3. Verification

The utility provides a console output summary:

List of deleted duplicate paths.

Total count of files removed.

Total reclaimed space (Optional extension).

📂 Project Structure

optimiser.py: The main automation script containing hashing and deletion logic.

test_files/: A sample directory structure to test duplicate detection.

# 👤 Author

Sakshi Bhapkar Final-Year Information Technology Engineering Student
