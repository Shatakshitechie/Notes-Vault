# Coding Style Guide (Shatakshi's Python style)

Derived from the practice notebook (if-else, loops, functions, comprehensions,
lambda/map/filter/reduce, file handling, exceptions, logging, mini-projects).
When writing Python for this user, follow these conventions exactly.

## Formatting
- **2-space indentation** in notebook cells (4-space only inside larger multi-line blocks like the calculator loops). Default to 2 spaces.
- Compact operators with **no spaces** in conditions and arithmetic: `num%2==0`, `i<=20`, `marks>=40`, `rev*10+(num%10)`, `i*i`.
  Spaces are used around `=` in assignments (`num = int(...)`), but sometimes dropped (`i=1`, `i=i+1`).
- Slightly looser spacing in `print`/f-string expressions and `range(1, 11)`; tight in `range(1,21)`. Mixed is natural—don't over-format.
- No type hints, no docstrings, no `if __name__ == "__main__":`. Code is flat, top-level, notebook-style.
- Comments are almost never used; the markdown cell above holds the question instead.

## Structure
- One question = one small cell. Markdown cell with the numbered question, then code, then an input-driven demo cell.
- Functions are defined in their own cell; the **call / input / print happens in the next cell**.
  Pattern: `def f(x): ... return ...` then `x = int(input(...))` then `print(f"... {f(x)}")`.
- Variables are short, plain, descriptive: `num`, `age`, `marks`, `temp`, `fac`, `rev`, `sum`, `i`, `name`, `choice`, `cont`, `again`.
  (It is fine to reuse built-in-like names such as `sum` — it's the user's habit, though avoid it when it would break later code.)
- Prefer simple, readable, beginner-level logic over clever one-liners — loops with accumulators (`fac = fac*i`, `sum = sum+i`) rather than `math.factorial` / `sum()` — **unless** the question explicitly asks for a feature (comprehension, lambda, map, filter, reduce).

## Input / Output
- Always take interactive input: `int(input("Enter a number: "))` (use `float(...)` when decimals make sense, e.g. positive/negative check, calculator, division).
- Prompt text is short, natural, ends with `: ` (e.g. `"Enter the marks: "`).
- Output uses **f-strings** almost exclusively: `print(f"{num} is an even number.")`, `print(f"{num}! = {fac}")`, `print(f"Total sum = {sum}")`.
- Output messages are plain English sentences, usually ending with a period (`"The person is eligible to vote."`), sometimes `...!` or `!!!` for friendly messages in menu programs.
- Label-then-value style: `Percentage = 62.0%`, `Grade: C`, `Maximum number in the list is 89`.

## Control flow habits
- `if / elif / else` chains ordered so later branches rely on earlier ones (e.g. `elif marks>=75` rather than re-checking an upper bound).
- Menu programs use `while True:` with an int choice, `if/elif/else` dispatch, and `break` on exit; a final `else:` prints an "invalid" message.
- "Do you want to continue? y or n" loop pattern with `.lower()` and `break`.
- `for ... else` is used for search ("Student not found").
- Ternary expressions inside lambdas: `lambda a,b: a if a>b else b`, `lambda a: "Even" if a%2==0 else "Odd"`, and verbose `True if cond else False` in filter lambdas.

## Functional / comprehension style
- List comprehension: `[i*i for i in range(1,11)]`, `[i for i in numbers if i%2==0]`; loop var is `i`.
- Dict comprehension: `{i:i*i for i in range(1,6)}`.
- `map`/`filter` always wrapped as `list(map(lambda a: ..., data))`; lambda parameter is usually `a` (and `a,b` for reduce).
- Data (`numbers = [...]`) is defined in its own cell before use.
- Complex mapping logic is put in a named `def` (e.g. `grade`, `prime`) and passed to `map`/`filter`.
- `from functools import reduce` in its own cell.

## Files
- Always use `with open(name, 'w'/'r'/'a') as file:` (variable `file`, or `f` in project code).
- Records stored as `name,marks\n` CSV-like lines; read with `line.strip().split(',')`.
- Small helper functions per operation: `add_stud`, `view_all`, `search_stud`, `withdraw`, `createAccount` (mix of snake_case and camelCase — snake_case preferred).

## Error handling
- `try / except` with **specific** exceptions (`ValueError`, `ZeroDivisionError`, `IndexError`, `FileNotFoundError`, `KeyError`), each with its own friendly message.
- Dictionary dispatch for operators: `ops = {'+': lambda a,b: a+b, ...}` and `KeyError` for wrong operator.
- Input validation loops (`while True` + `try` + `break`) when re-asking is needed (e.g. marks 0–100).

## Logging
- `import logging` in its own cell; `logging.basicConfig(filename="something.log", level=logging.INFO, force=True)` in its own cell.
- Log lots of small steps: `logging.info("Program started")`, per action/choice, `logging.error(...)` / `logging.warning(...)` for errors, `finally:` -> `"Program completed"`.
- Never log passwords/pins.

## Projects (larger programs)
- Data kept in a global dict (`accounts = {}`, `student = {}`) with list values (`[password, logged_in, balance]`).
- Menu text on multiple lines with `\n`, e.g. `"\n1.Withdrawal  2.Deposit  3.Check Balance\n4.Change pin  5.Exit\nChoose: "`.
- Each transaction appended to a `.txt` file and logged.

## Level / tone
- Beginner-to-intermediate, practical, exam/lab-practice oriented. Match this level: **simple, readable, correct, interactive**. Don't introduce classes, decorators, type hints, `argparse`, or advanced libraries unless asked.
