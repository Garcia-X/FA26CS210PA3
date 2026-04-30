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

---

## 2026-04-26
**Work:** DFS review + code cleanup
- Reviewed the completed DFS implementation against the assignment directions.
- Kept the recursive DFS, visited tracking, parent tracking, and path reconstruction in place.
- Removed extra ideas that were not needed in `main.cpp`.
- Kept the program output limited to the maze, the path when found, and `No path exists.` otherwise.

**Testing:**
- Confirmed that the current version still matches the required DFS behavior.
- Kept the code ready for future final review before submission.

**Commit:** (Day 6: review DFS implementation and clean up code)

---

## 2026-04-27
**Work:** Boundary-cell validation for maze generation
- Added a `countOpenBoundaryCells(...)` helper to count open cells on the maze boundary.
- Updated `main()` to regenerate the maze until there are at least two open boundary cells available.
- Kept the provided helper functions unchanged.
- Kept the DFS logic, parent tracking, and output format the same.

**Testing:**
- Built the project successfully in CLion.
- Ran the program with multiple maze sizes and confirmed that the maze still prints normally.
- Confirmed that the program still prints the path when one exists and `No path exists.` otherwise.
- Verified that the maze setup now avoids bad random cases where entrance and exit selection could get stuck.

**Commit:** (Day 7: validate boundary cells before choosing entrance and exit)

---

## 2026-04-28
**Work:** Distinct boundary-cell handling
- Replaced the earlier boundary check with `countDistinctOpenBoundaryCells(...)` so boundary cells are counted by unique position.
- Fixed the corner and single-row / single-column case where the same boundary cell could be counted more than once.
- Kept the provided helper functions unchanged.
- Kept the DFS logic, parent tracking, and output format the same.

**Testing:**
- Built the project successfully in CLion.
- Ran the program with multiple maze sizes and confirmed that the maze still prints normally.
- Confirmed that the program still prints the path when one exists and `No path exists.` otherwise.
- Verified that the maze setup now checks for two distinct boundary positions before choosing entrance and exit.

**Commit:** (Day 8: handle distinct boundary cells in maze setup)

---

## 2026-04-29
**Work:** Small-maze edge case handling
- Added a `hasEnoughBoundaryCells(...)` helper to make the maze setup check more readable.
- Added a special-case check for `1 x 1` mazes, since two distinct boundary positions are impossible in that case.
- Kept the provided helper functions unchanged.
- Kept the DFS logic, parent tracking, and output format the same.

**Testing:**
- Built the project successfully in CLion.
- Ran the program with `1 1`, `1 5`, `5 1`, and other small maze sizes.
- Confirmed that normal mazes still print the path when one exists and `No path exists.` otherwise.
- Verified that the `1 x 1` case exits cleanly instead of getting stuck in maze setup.

**Commit:** (Day 9: handle small maze edge cases

---

## 2026-04-30
**Work:** Final maze setup and edge-case cleanup
- Reviewed the completed DFS implementation and kept the recursive search, visited tracking, parent tracking, and path reconstruction unchanged.
- Added helpers to collect unique boundary cells and count distinct open boundary positions.
- Added `ensureTwoOpenBoundaryCells(...)` so the maze always has enough valid boundary cells for different entrance and exit positions.
- Added a `1 x 1` edge-case check so the program exits cleanly instead of getting stuck trying to choose two different boundary cells.

**Testing:**
- Built the project successfully in CLion.
- Ran the program with normal maze sizes and confirmed that the maze, path output, and no-path output still work.
- Tested small edge cases such as `1 1`, `1 5`, and `5 1`.
- Confirmed that the maze setup no longer depends on repeated regeneration to find valid boundary cells.

**Commit:** (Day 10: final cleanup + boundary setup + small-maze handling)