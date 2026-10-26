## 1. Review Checklist

The checklist checks initialization, pointers, arrays/buffers, loops, arithmetic, control flow, function calls, and memory management.

| No. | Category | Result (Issue/OK) | Defect / Observation |
|---:|---|---|---|
| 1 | Initialization | Issue | `sum` in `averageAttack()` is not initialized. |
| 2 | Pointers | Issue | `attackMonster()` and `getMonsterLabel()` may dereference a null pointer. |
| 3 | Arrays / Buffers | Issue | `spawnMonster()` can exceed the array capacity. `readBoss()` can overflow its character buffer. |
| 4 | Loops | Issue | `totalMonsterHealth()` uses `i <= monsterCount`, causing an out-of-bounds access. |
| 5 | Arithmetic | Issue | Unsigned damage, integer division, and division by zero can produce incorrect results. |
| 6 | Control Flow | Issue | `playerRank()` has no return statement for scores of 100 or below. |
| 7 | Function Calls | Issue | `findMonster()` uses assignment instead of comparison. Other functions also use unsafe results. |
| 8 | Memory Management | Issue | Memory leaks, use-after-free, double deletion risks, and shallow copying are present. |
