# Academia Portal - Course Management System

A robust, multi-user Course Management System built in C using socket programming and multithreading. This application allows Administrators, Faculty, and Students to manage courses, enrollments, and user profiles in a concurrent environment.

## 🚀 Features

### Core Functionality
- **Role-Based Access Control**: Distinct menus and permissions for Admins, Faculty, and Students.
- **Course Management**: Create, update, view, and remove courses.
- **Enrollment System**: Students can enroll/unenroll; Faculty can view enrollments.
- **User Management**: Admins can manage student and faculty accounts.

### Technical Highlights
- **Client-Server Architecture**: TCP/IP socket communication.
- **Concurrency**: Multithreaded server handling multiple clients simultaneously.
- **Data Persistence**: File-based storage for users, courses, and enrollments.
- **Synchronization**: Use of semaphores and file locking (read/write locks) to ensure data integrity during concurrent access.

## 🛠️ Technology Stack
- **Language**: C
- **Libraries**: `pthread` (threading), `sys/socket` (networking), `semaphore` (synchronization)
- **Platform**: Linux/Unix-based systems (requires POSIX support)

## 📋 Prerequisites
- GCC Compiler
- Make (optional, if a Makefile is added later)
- Linux environment (or WSL on Windows)

## ⚙️ Compilation & Setup

1. **Compile the Server**:
   ```bash
   gcc -Wall -pthread -o server server.c
   ```

2. **Compile the Client**:
   ```bash
   gcc -o client client.c
   ```

3. **Initialize Data Files** (First Run):
   The server will automatically create `users.txt`, `courses.txt`, and `enrollments.txt` if they don't exist, initializing with a default Admin account.

## 🚀 Usage

1. **Start the Server**:
   ```bash
   ./server
   ```

2. **Start a Client** (in a new terminal):
   ```bash
   ./client
   ```

### Default Login
- **Username**: `admin`
- **Password**: `admin123`

### User Roles & Capabilities

#### 👤 Admin
- Add Students, Faculty, and other Admins.
- Activate/Deactivate Student accounts.
- Update user details (passwords, usernames).
- View all users and courses.

#### 🎓 Student
- View available and enrolled courses.
- Enroll in new courses (subject to seat availability).
- Unenroll from courses.
- Change password.

#### 👨‍🏫 Faculty
- Add new courses (specifying seats and name).
- Remove offered courses.
- View enrollments in their courses.
- Change password.

## 📂 Project Structure
- `server.c`: Main server logic, connection handling, and data synchronization.
- `client.c`: Client-side interface and server communication.
- `users.txt`: Stores user credentials and metadata.
- `courses.txt`: Stores course details (ID, Code, Name, Seats).
- `enrollments.txt`: Maps students to courses.
