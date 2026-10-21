# General Coding Rules

## 0 — Purpose

These rules ensure maintainability, safety, and developer velocity.
**MUST** rules are always followed; **SHOULD** rules are strongly recommended.

---

## 1 — Before Coding

- **BP-1 (MUST)** Ask the user clarifying questions when the requirement is unclear.
- **BP-2 (SHOULD)** Draft and confirm an approach for complex work.
- **BP-3 (SHOULD)** If ≥ 2 approaches exist, list clear pros and cons.
- **BP-4 (MUST)** Read the related existing code before changing it.

---

## 2 — While Coding

- **C-1 (MUST)** DRY: one purpose, one piece of code. Before writing, search for existing code that does the same job and reuse it.
- **C-2 (SHOULD NOT)** Merge code that only looks similar but serves a different purpose — that is not repetition.
- **C-3 (MUST)** Follow the project's existing folder and file structure. In a new project, group files by feature (e.g. `students/`, `exams/`).
- **C-4 (SHOULD)** Keep one clear purpose per file; split a file when it mixes unrelated things.
- **C-5 (MUST)** One function does one job, with a clear name in the project's own words.
- **C-6 (MUST)** Give every file, class and function a short plain-language description: what it takes, what it does, what it gives back.
  ```python
  def get_pass_percentage(marks: list[int], pass_mark: int) -> float:
      """Takes a list of student marks and the pass mark,
      counts how many students passed, and returns the pass percentage (0–100)."""
  ```
- **C-7 (SHOULD NOT)** Use classes when simple functions are enough; use a class only when data and its behaviour belong together.
- **C-8 (MUST)** Validate all outside input (forms, API requests, files, env vars) with a schema — Pydantic in Python, Zod in JS/TS.
- **C-9 (MUST)** No magic numbers or strings; use named constants kept in one place.
- **C-10 (MUST)** Keep secrets and settings in environment variables, never in code.
- **C-11 (MUST NOT)** Ignore errors silently; handle them or show a clear message.
- **C-12 (SHOULD)** Inside the code, comment only *why* something is done, not *what* it does.
- **C-13 (MUST NOT)** Add a new library without asking.
- **C-14 (MUST)** Before finishing, remove debug prints, temp files and commented-out code.

---

## 3 — Testing

- **T-1 (MUST)** Write tests together with the code, and run them before saying the work is done.
- **T-2 (MUST)** Run the existing tests too, so nothing else breaks.
- **T-3 (MUST)** Test the normal case, edge cases (empty, zero, very large) and wrong input.
- **T-4 (MUST)** For a bug fix, first write a test that fails because of the bug, then fix it.
- **T-5 (MUST NOT)** Write tests that can't fail (e.g. `assert True`) or that use the function's own output as the expected answer.
- **T-6 (SHOULD)** Use the project's test tool (pytest for Python, Vitest/Jest for JS) and its test folder layout.
- **T-7 (SHOULD)** Mock only outside services (payments, email, third-party APIs); test real logic for real.
- **T-8 (MUST)** When done, report which files changed, what was tested and what wasn't, and any risks (DB change, new env variable).
- **T-9 (MUST)** For anything you couldn't test yourself, give the user a manual test list. For each item: **how** (exact command or click steps), **why** it needs checking, and **expected** result.
  ```
  1. Postgres tests
     How: run `.venv/bin/pytest tests/test_team.py`
     Why: the new query only runs on real Postgres, not the test database
     Expected: all tests pass, e.g. "5 passed"
  ```

---

## 4 — Never Without Asking

- **N-1 (MUST NOT)** Commit or push to git without asking.
- **N-2 (MUST NOT)** Delete an existing file, or replace a whole file from scratch, without asking. Normal edits inside files need no asking. Files created in the same task (temp files, debug scripts) may be cleaned up.
- **N-3 (MUST NOT)** Run destructive database commands (`DELETE`, `DROP`, `TRUNCATE`, bulk `UPDATE`) on real data without asking. A local test database created for testing is fine.
- **N-4 (MUST NOT)** Change anything live (deploy, production database, live settings) without asking.
