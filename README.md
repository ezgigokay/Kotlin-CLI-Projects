# 🖥️ Kotlin Console Apps

Two small command-line applications written in Kotlin, demonstrating core programming concepts including OOP, data classes, collections, loops, conditions, and file I/O.

---

## Projects

### 1. 📝 Task Manager

A console-based task management app with persistent file storage.

**Features:**
- Add, delete, and list tasks
- Mark tasks as complete
- Search tasks by name
- Filter and list only completed tasks
- Save all tasks to a `.txt` file

**Architecture:**

```
model/Task.kt          → Task data class + TaskStatus enum
core/TaskManager.kt    → Business logic (add, delete, list, search, save)
cli/TaskCli.kt         → CLI adapter (reads input, calls TaskManager, prints output)
```

**Concepts used:** `data class`, `enum class`, `MutableList`, `when`, `filter`, `find`, `File I/O`

---

### 2. 📚 Smart Library

A console-based library management system for books, members, and loan records.

**Features:**
- Initialize a book catalog with preset books
- Add new books and members
- Borrow books (creates a loan record with due date)
- Search books by title
- View all transactions and currently borrowed books

**Architecture:**

```
SmartLibrary.kt  → SmartLibrary class with all menus and logic
                   + Book, Members, LoanRecord data classes
                   + Global catalog (Map), members (Set), transaction (List)
```

**Concepts used:** `open class`, `data class`, `MutableMap`, `MutableSet`, `MutableList`, `LocalDate`, nested menus with `while` loops

---

## Tech Stack

- **Language:** Kotlin (JVM)
- **Build:** Gradle (Kotlin DSL)
- **Testing:** JUnit 4 (TaskManager unit tests)

---

## Project Structure

```
cli/
├── src/
│   ├── main/kotlin/com/example/consoleapp/
│   │   ├── cli/TaskCli.kt           # CLI adapter for Task Manager
│   │   ├── core/TaskManager.kt      # Task Manager business logic
│   │   ├── model/Task.kt            # Task data model
│   │   └── SmartLibrary.kt          # Smart Library (all-in-one)
│   └── test/kotlin/com/example/consoleapp/
│       └── TaskManagerTest.kt       # Unit tests for TaskManager
```

---

## Tests

`TaskManagerTest` covers the core `TaskManager` logic:
- Adding a task creates it with correct title and default status
- Completing a task updates its status to `DONE`
- Deleting a task removes it from the list
- Saving tasks writes them to a file

---

## How to Run

Open in **IntelliJ IDEA** or **Android Studio**, then run:

- **Task Manager:** run `main()` in `TaskCli.kt`
- **Smart Library:** run `main()` in `SmartLibrary.kt`

Or via Gradle:

```bash
./gradlew :cli:run
```

