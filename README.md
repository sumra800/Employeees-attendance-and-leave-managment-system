# Employee Attendance and Leave Management System

A C++ based console application designed to manage employees, track their daily attendance, and process leave applications through a hierarchical approval workflow.

## Features

* **Role-Based Access Control System:**
  * **Employee:** Can apply for leaves, view their own leave details, and check attendance reports.
  * **Guard:** Responsible for marking the daily attendance of employees.
  * **Supervisor:** Reviews and makes decisions on short leave applications (up to 4 days).
  * **Director:** Reviews and makes decisions on extended leave applications (more than 4 days).
  * **Admin:** Manages the overall system records.

* **Attendance Management:**
  * Keep track of Present, Absent, on Leave, or Out days.
  * Guards mark attendance status.
  * Auto-reconciliation: Automatically caters for unmarked absences by deducting available Casual Leaves as "Outstanding Leave".
  * Real-time Weekly and Monthly attendance reports indicating total working hours and days present/absent.

* **Leave Management System:**
  * Four distinct types of leaves supported: `Casual`, `Earned`, `Official`, and `Unpaid`.
  * Configurable leave balances for each employee (e.g., 15 Casual, 21 Earned leaves).
  * Leave application status tracking (Pending, Approved, Rejected).

* **Data Persistence:**
  * File-based storage using polymorphic `FileManager` classes.
  * Data is saved locally in CSV formats to `attendance_data.txt` and `leave_data.txt` for continuous record keeping.

## Files

- `source_code.cpp`: Contains the entire core logic, class implementations (Employee, Leave forms, Approvals, Manager), and CLI loop in the `main` function.
- `attendance_data.txt`: Generated file storing user attendance records.
- `leave_data.txt`: Generated file storing user leave applications and their current processing status.

## Technologies Used

- **Language**: C++ (Standard C++11 or higher recommended)
- **Concepts**: Object-Oriented Programming (Polymorphism, Inheritance, Encapsulation), File I/O, Vectors.

## Getting Started

### Prerequisites

You need a C++ compiler installed on your system. For example, GCC (`g++`) or MSVC.

### Compilation & Execution

1. Clone or download the repository to your local machine.
2. Open a terminal or command prompt in the project directory.
3. Compile the code:
   ```bash
   g++ source_code.cpp -o attendance_system
   ```
4. Run the executable:
   - On Windows:
     ```cmd
     attendance_system.exe
     ```
   - On Linux/macOS:
     ```bash
     ./attendance_system
     ```

## Usage Flow

Upon running, you'll be greeted with a menu asking to choose a role:
`E` for Employee, `S` for Supervisor, `G` for Guard, `D` for Director, `A` for Admin, and `X` to Exit.

Select the corresponding identity character and follow the respective CLI prompts to log attendance, apply for vacations, or approve pending leaves.
