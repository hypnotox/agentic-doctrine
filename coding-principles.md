# Coding principles

These principles specialize the [working principles](working-principles.md) for code design, implementation, and review.

## 1. Give each concern one authoritative home.

Keep each policy, changing fact, and piece of authoritative state owned in one place. Keep responsibilities together when they change for the same reason; avoid coupling concerns that change independently. Share code because it shares meaning, not merely because it looks similar.

## 2. Write code that reveals its model.

Use clear names and straightforward control flow. Make meaningful state, invariants, dependencies, and data flow understandable. Separate domain policy from external details where this improves understanding and change; introduce abstractions to serve real boundaries, not to satisfy a pattern.

## 3. Prefer clean integration to accumulated workarounds.

Assess whether a change fits the existing model, and propose bounded refactors when they resolve a concrete correctness or maintenance problem. Remove superseded paths once they are no longer needed by supported consumers. Do not make unrelated cleanup a prerequisite.

## 4. Reuse suitable capabilities before building alternatives.

Use existing codebase, platform, and dependency capabilities when they meet the need cleanly. Do not recreate an available mechanism without a concrete reason, or force reuse where the behavior does not fit. Judge dependencies and wrappers by the complexity they remove and introduce.

## 5. Make failure behavior explicit.

Keep failure distinguishable from valid results. Make error reports identify what failed and why, when known. Recover or fall back only when the resulting behavior has a defined meaning and still satisfies the relevant contract. Do not conceal errors behind defaults or apparent success.

## 6. Do not invent defensive requirements.

Follow the project’s established stance on defensive development and testing. When none is defined, implementing the agreed behavior and verifying it with straightforward tests of normal operation and relevant edge cases is sufficient. Do not add safeguards or tests for hypothetical threats, races, duplicate writes, or other scenarios without a basis in actual use or established contracts. Broader defenses and coverage need an explicit requirement or a concrete, project-specific risk; surface that risk rather than silently expanding scope.

## 7. Test behavior and contracts.

Exercise agreed outcomes and relevant failure cases, not incidental structure or wording. Choose tests that can reveal meaningful regressions; avoid tests that merely restate the implementation.
