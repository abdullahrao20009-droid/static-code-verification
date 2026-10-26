| No. | Code Location | Defect Type | Why It Is a Problem | Proposed Fix | Severity |
|---:|---|---|---|---|---|
| 1 | `spawnMonster()` | Array out of bounds | More than five monsters can be inserted into a five-element array. | Check capacity before insertion. | Critical |
| 2 | `findMonster()` | Assignment instead of comparison | `=` changes the monster ID instead of comparing it. | Replace `=` with `==`. | High |
| 3 | `attackMonster()` | Null pointer dereference | A missing monster returns `nullptr`, which is dereferenced. | Check whether `m == nullptr`. | High |
| 4 | `attackMonster()` | Signed/unsigned error | Negative damage converts to a large unsigned value. | Validate damage and use safe signed arithmetic. | High |
| 5 | `totalMonsterHealth()` | Loop boundary error | `i <= monsterCount` accesses an invalid array element. | Change the condition to `i < monsterCount`. | High |
| 6 | `getMonsterLabel()` | Dangling reference | The function returns a reference to a local string that is destroyed. | Return `std::string` by value. | High |
| 7 | `averageAttack()` | Uninitialized variable | `sum` contains an indeterminate value. | Initialize `sum` to `0.0`. | High |
| 8 | `averageAttack()` | Division by zero | An empty monster collection causes division by zero. | Check whether `monsterCount == 0`. | Medium |
| 9 | `defeatMonster()` | Use-after-free | The monster's name is accessed after deletion. | Print the name before deletion and remove the pointer from the collection. | Critical |
| 10 | `calculateDamage()` | Integer division | Fractional damage results are truncated. | Divide by `100.0`. | Medium |
| 11 | `playerRank()` | Missing return | Some scores reach the end without returning a value. | Add a return for the remaining cases. | High |
| 12 | `readBoss()` | Buffer overflow | Input may exceed the ten-character buffer. | Use `std::string` for the name. | Critical |
| 13 | `readBoss()` | Incorrect deallocation | `new char[10]` is paired with `delete` instead of `delete[]`. | Use `delete[]` or eliminate manual allocation. | High |
| 14 | `Game()` | Initialization issue | The pointer array is not initialized. | Initialize pointers to `nullptr` or use a container. | Medium |
| 15 | `main()` | Memory leak | The dynamically allocated `bonus` monster is never deleted. | Use a smart pointer or release the memory safely. | Medium |
| 16 | `Game copy = game;` | Shallow copy | Both objects own the same pointers, risking double deletion. | Implement deep copying or disable copying. | Critical |
| 17 | `main()` | Invalid monster ID | `attackMonster(99, 20)` requests a nonexistent monster. | Handle missing IDs safely. | High |
| 18 | `defeatMonster()` | Missing validation | The function does not verify that the monster exists. | Check for `nullptr` before accessing the monster. | High |
| 19 | `spawnMonster()` | Missing capacity validation | No check prevents insertion beyond `MAX_MONSTERS`. | Validate capacity or use a dynamic container. | Critical |
| 20 | `readBoss()` | Unnecessary allocation | A character array is copied into a `std::string`. | Read directly into `std::string`. | Medium |
| 21 | `averageAttack()` | Return type mismatch | Returning `int` discards the fractional average. | Return `double`. | Low |
| 22 | `Game` copy/destructor | Unsafe ownership | Raw pointers are copied without safe ownership handling. | Follow the Rule of Three/Five or use smart pointers. | Critical |
