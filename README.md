# Library Management System

## Overview
This project is a Java-based Library Management System (BCI) for my Object-Oriented Programming class. It features a robust domain model for managing library users, various types of works (such as Books and DVDs), and a complete workflow for borrowing and returning items. The application is driven by a text-based user interface (CLI).

## Features

### User Management
* **Register Users**: Add new users to the library system.
* **User States**: Users are classified into different states (`Normal`, `Cumpridor` / Compliant, `Faltoso` / Defaulting) based on their behavior (e.g., returning works on time).
* **Fines System**: Handle overdue fines for users who fail to return works on time. Users cannot borrow new works until their fines are paid.
* **Notifications**: Users can be notified when a previously unavailable work becomes available for borrowing.

### Work Management
* **Catalog Management**: Manage different types of works, primarily Books and DVDs.
* **Inventory Control**: Update and track the number of available copies for each work.
* **Search and Display**: Search for works by ID, display works by specific creators, or list all available works.

### Request/Borrowing System
* **Borrow Works**: Users can request to borrow works. The system validates requests against multiple business rules (e.g., checking if the user is suspended, if there are available copies, simultaneous request limits, and price limits).
* **Return Works**: Process returned works, automatically calculating fines if they are late and triggering notifications for other users waiting for the work.

### State Persistence
* **Save/Load**: The current state of the library can be saved to a file and loaded later, ensuring no data is lost between sessions.
* **Import Data**: Supports importing initial data from text files.

## Project Architecture

The project follows a clear separation of concerns, divided mainly into core logic and application interface:

* **`bci.core`**: Contains the business logic and domain entities (`Library`, `LibraryManager`, `User`, `Work`, `Request`, rules, and states).
* **`bci.app`**: Contains the command classes for the text-based interface, organized by menus (`main`, `user`, `work`, `request`).
* **`pt.tecnico.uilib`**: A custom text-based user interface framework used to render menus, prompts, and handle user input.

## Getting Started

### Prerequisites
* Java Development Kit (JDK) 11 or higher.
* Make or a compatible shell to run the provided scripts.

### Compiling and Running
To compile the project, you can use the provided Makefile:
```bash
make
