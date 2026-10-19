> **ANSWER KEY (check the class against this)**
>
> - Five files exist and are valid: issue form, `copilot-instructions.md`, `tests.instructions.md`, `devcontainer.json`, `copilot-setup
teps.yml`, plus `docs/task-contract-issue-2.md`.
> - `copilot-instructions.md` is about **19 lines (~230 tokens)** versus **74 lines (~1,100 tokens)** for `AGENTS.md`.
> - The issue form appears under **New issue** only **after** the work is merged into the default branch. The setup job must be named exa
ctly `copilot-setup-steps`.
> - Unit tests: **81 passed**.
> - Compare any file: `git show worked-example:<path>`; the commit is `git log worked-example --oneline --grep="Lab 1.2"`.
> **WHAT THEY LEARNED**
>
> They can write a task contract, set up layered instructions, and make an environment reproducible. They used these skills by building a
ll five files and converting issue 2 into a contract.
> **MODULE RECAP: Task contracts and repo context**
>
> **Learned:** the seven contract fields; three layers of instructions; why short instructions win; why environments must be reproducible
; that instruction files are guidance, not enforcement.
>
> **Used in the lab:** wrote the issue form, the instructions file, the tests rules, the dev container and the setup file, and turned iss
ue 2 into a contract.
# Task contract: issue 2, delivered orders can be cancelled
**Goal:** Delivered orders must not be cancellable (issue #2).
**Context:** AGENTS.md (order state machine), tests/unit/test_orders.py
**In scope:** app/modules/orders/service.py, tests/unit/test_orders.py, tests/integration/test_orders.py
**Out of scope:** alembic/, .github/, pyproject.toml, any new dependency
**Acceptance:**
- a new unit test fails on the current code and passes after the fix
- POST /orders/{id}/cancel on a delivered order returns 400
- `python -m pytest tests/unit -q` passes
**Stop and ask a human if:** the fix needs a schema change or a change in the payment module
**Reviewer:** your second account
