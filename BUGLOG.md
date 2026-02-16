

1) Menu selection syntax error
   Bug: `if opt = "1":`
   Fix: changed to `if opt == "1":`

2) Loading loop infinite
   Bug: `loading` never increments
   Fix: added `loading += 1`

3) Menu blocked by stray loop
   Bug: stray `while True: ...` prevented reaching the menu
   Fix: removed that loop

4) Program didn’t run
   Bug: function not called / missing proper entry point
   Fix: added `if __name__ == "__main__": run_system_monolith()`

5) View Crew index error
   Bug: `for i in range(10)` caused IndexError
   Fix: loop uses `min(len(...))`

6) Add Crew list misalignment
   Bug: only name appended (rank/division not appended)
   Fix: append to `n`, `r`, and `d`

7) Remove Crew crash when name missing
   Bug: `n.index(rem)` raised ValueError if name not found
   Fix: check `if rem in n:` before using `.index()`

8) Analyze Data logic always true
   Bug: `if rank == "Captain" or "Commander":` always evaluates true
   Fix: `if rank == "Captain" or rank == "Commander":`

9) Analyze Data type error printing count
   Bug: `"High ranking officers: " + count` (str + int)
   Fix: cast with `str(count)`

10) Database message logic duplicated
   Bug: two separate `if` statements could be inconsistent
   Fix: used `elif/else` so only one message prints
