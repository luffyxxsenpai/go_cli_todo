Below is a **clean, production-ready GitHub README** you can paste directly into `README.md`.

---

# 📝 Go Todo CLI

A simple, fast **command-line Todo application written in Go**.
It supports adding, editing, deleting, toggling, listing todos, and **persists data to a JSON file**.

This project is intentionally minimal and idiomatic, showcasing:

* Go methods & interfaces
* Pointer receivers
* Generics for storage
* CLI flag parsing
* Table-based terminal output

---

## ✨ Features

* ➕ Add todos
* ✏️ Edit existing todos
* 🔁 Toggle completion status
* ❌ Delete todos
* 📋 List all todos in a table
* 💾 Persistent storage using JSON
* ⚡ Fast, dependency-light CLI

---

## 📦 Project Structure

```
.
├── main.go        # Entry point
├── command.go     # CLI flags & command execution
├── todo.go        # Todo domain logic
├── storage.go    # Generic JSON storage layer
├── todos.json    # Auto-created data file
```

---

## 🚀 Getting Started

### Prerequisites

* Go **1.20+**

### Install dependencies

```bash
go mod tidy
```

### Build

```bash
go build -o todo
```

### Run

```bash
./todo
```

---

## 🧠 Usage

### Add a todo

```bash
./todo -add "buy milk"
```

### Edit a todo

```bash
./todo -edit 0:buy almond milk
```

### Toggle completion

```bash
./todo -toggle 0
```

### Delete a todo

```bash
./todo -del 0
```

### List all todos

```bash
./todo -list
```

---

## 📋 Example Output

```
+---+-------------------+-----------+---------------------------+---------------------------+
| # | Title             | Completed | Created At                | Completed At              |
+---+-------------------+-----------+---------------------------+---------------------------+
| 0 | buy milk          | ✅        | Mon, 02 Jan 2026 15:04:05 | Mon, 02 Jan 2026 15:10:01 |
| 1 | read Go book      | ❌        | Mon, 02 Jan 2026 15:06:42 |                           |
+---+-------------------+-----------+---------------------------+---------------------------+
```

---

## 💾 Storage Design

Todos are stored in `todos.json` using a **generic storage layer**:

```go
storage := NewStorage[Todos]("todos.json")
storage.Load(&todos)
storage.Save(todos)
```

* Uses Go generics (`Storage[T]`)
* JSON is human-readable
* File is auto-created on first save

---

## 🧩 Key Concepts Demonstrated

* **Pointer receivers** for slice mutation
* **Implicit interface satisfaction**
* **Generics** for reusable storage
* **Flag-based CLI design**
* **Optional fields** using pointers (`*time.Time`)
* **Separation of concerns**

---

## 🛠️ Dependencies

* [`github.com/aquasecurity/table`](https://github.com/aquasecurity/table)
  Used for clean terminal table rendering.

---

## 📌 Notes

* Invalid commands are safely handled
* Index validation prevents panics
* Designed as a learning-friendly but real-world CLI

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 👤 Author

Built as a hands-on Go learning project.

---