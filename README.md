# Lua pairs iterator and recursive table traversal

This repository demonstrates a potential issue with Lua's `pairs` iterator when used in recursive functions that modify tables during iteration.  The problem arises because `pairs` iterates over the table as it exists at the start of the iteration, and won't see keys added during the iteration.

## Bug Description
The `bug.lua` file contains a function `foo` that recursively traverses a nested table.  The issue appears when the table is modified during the traversal, leading to incomplete iteration and unexpected behavior.

## Solution
The `bugSolution.lua` file provides a corrected version of the function which avoids the issue.