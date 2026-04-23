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

---

## 2026-04-22
**Work:** DFS traversal logic
- Added DFS base case checks for out-of-bounds positions, walls, and previously visited cells.
- Marked each visited cell inside `dfs(...)`.
- Added the exit check so DFS returns `true` when it reaches the exit.
- Added the 4-direction traversal loop using `dr` and `dc`.
- Added recursive DFS calls so the search now explores the maze.
- Temporarily changed the success output to `A path exists.` since parent tracking is not implemented yet.

**Testing:**
- Built the project successfully in CLion.
- Ran the program with small maze sizes such as `5 5`.
- Confirmed that the program reports whether a path exists.
- Left path reconstruction for the next work session.

**Commit:** (Day 2: implement DFS traversal logic)

---

## 2026-04-23
**Work:** Parent tracking + path reconstruction
- Added parent tracking in `dfs(...)` using `parent_r` and `parent_c`.
- Set each neighbor’s parent before making the recursive DFS call.
- Kept the DFS base cases, visited marking, exit check, and 4-direction traversal.
- Restored the final output in `main()` so successful searches call `printPath()` again.

**Testing:**
- Built the project successfully in CLion.
- Ran the program with small maze sizes such as `5 5`.
- Confirmed that mazes with a path now print the reconstructed path.
- Confirmed that mazes without a path still print `No path exists.`

**Commit:** (Day 3: add parent tracking and path reconstruction)