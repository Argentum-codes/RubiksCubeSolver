# 🧊 Rubik's Cube Solver in C++

This is a C++ project that implements a 3×3 Rubik’s Cube solver using **Object-Oriented Programming** principles and classic **search algorithms** such as BFS, DFS, IDDFS, and IDA\*.

---

## 📌 Features

- Cube representation using a **3D array**
- **Move execution**, **move inversion**, and **random shuffling**
- **Abstract base class** for general cube operations
- Operator overloading (`==`, hash function) for STL container support
- Solvers:
  - **Breadth-First Search (BFS)**
  - **Depth-First Search (DFS)**
  - **Iterative Deepening DFS (IDDFS)**
  - **Iterative Deepening A\* (IDA\*)**

---

## 🧱 Object-Oriented Structure

### `RubiksCube` (Abstract Base Class)

- Declares core functionalities:
  - `move(Face f, int times)`
  - `isSolved()`
  - `print()`
  - `getCornerIndex()`
  - `getCornerOrientation()`
- Allows flexibility for multiple internal representations

### `RubiksCube3DArray` (Concrete Class)

- Implements cube as `colors[6][3][3]` array
- Supports all required operations
- Implements:
  - `operator==` to compare cube states
  - `std::hash` to use in `unordered_set` and `unordered_map`

---

## 🔍 Search Algorithms

### ✅ BFS (Breadth-First Search)
- Guarantees shortest solution
- May consume a lot of memory

### ✅ DFS (Depth-First Search)
- Explores deeper paths first
- Risk of infinite recursion if not bounded

### ✅ IDDFS (Iterative Deepening DFS)
- Memory-efficient
- Combines DFS with BFS-like completeness

### ✅ IDA\* (Iterative Deepening A\*)
- Uses heuristic + depth
- Efficient on large search spaces

---

## ⚙️ How to Build and Run (in CLion or Terminal)

### CLion
1. Right-click `project root` → **New → Directory** → name it (e.g., `src`)
2. Move all `.cpp` and `.h` files into `src`
3. Ensure `CMakeLists.txt` includes:
   ```cmake
   add_executable(RubiksCubeSolver src/main.cpp)
