# DEVLOG

## 2026-04-21
**Work:** Project setup + DFS prep
- Forked the assignment repo and cloned it into CLion.
- Added `CMakeLists.txt` so the project would build in CLion.
- Added `.gitignore` for CLion and CMake build files.
- Read through `README.md`, `OURPUTguide.md`, and `main.cpp`.
- Located the maze grid, visited array, parent arrays, entrance/exit variables, DFS placeholder, and DFS call spot in `main.cpp`.
- Added the `dfs(...)` function stub.
- Connected the DFS call and the path / no-path output block in `main()`.

**Testing:**
- Built the project successfully in CLion.
- Ran the program with `5 5`.
- Confirmed that the maze prints correctly.
- Confirmed that the current DFS stub compiles and the program prints `No path exists.`

**Commit:** (Day 1: project setup + DFS prep)