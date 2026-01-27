# fastapi-auth-spec
This repository is a **minimal FastAPI authentication service designed to demonstrate spec-driven development using SpecLeft.

The project intentionally includes:
- Clearly defined behavioral requirements
- Skeleton tests that express intent before implementation
- CI enforcement that fails when behavior and tests diverge

The goal is not feature completeness, but **behavioral clarity**:
each test describes *what the system must do*, and enforcement ensures the code actually does it.

This repository is optimised for use with AI coding agents.
Behavioral intent is explicit, deterministic, and easy to verify.

For more details on spec driven development with SpecLeft: [https://github.com/SpecLeft/specleft](https://github.com/SpecLeft/specleft)

## Agent Guidance

When modifying this repository:
- Do not add new features unless explicitly specified
- Preserve existing behavioral tests
- Prefer failing fast over guessing intent
- Behavior defined in tests is authoritative