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

---

## 2026-04-24
**Work:** Input validation + program cleanup
- Added input validation in `main()` for maze dimensions. 
- Checked for failed input before building the maze.
- Rejected non-positive maze sizes with a clear message.
- Kept the DFS logic and provided helper function unchanged.

**Testing:**
- Built the project succesfully in CLion.
- Ran Valid input such as `5 5` and confirmed the maze and DFS output still work.
- Tested invalid input cases such as `0 5`, negative values, and non-numeric input `a b`.
- Confirmed the program exits cleanly with an error message for invalid input.

**Commit:** (Day 4: add input validation and test program behavior.)

---

## 2026-04-25
**Work:** DFS cleanup + debug support
- Refactored the DFS logic by adding a `canVisit(...)` helper to handle bounds, wall, and visited checks in one place.
- Simplified `dfs(...)` so the recursion logic is easier to read.
- Kept parent tracking and path reconstruction behavior unchanged.
- Added optional DFS debug output controlled by a `DEBUG_DFS` flag.

**Testing:**
- Built the project successfully in CLion.
- Ran the program with valid maze sizes and confirmed that path printing still works.
- Confirmed that blocked mazes still print `No path exists.`
- Verified that turning debug output off keeps the normal assignment output clean.

**Commit:** (Day 5: refactor DFS and add optional debug tracing)