# Coding principles

These principles specialize the [general principles](general-principles.md) for code design, implementation, and review.

## 1. Keep responsibilities cohesive.

Keep responsibilities together when they change for the same reason; avoid coupling concerns that change independently. Share code because it shares meaning, not merely because it looks similar.

## 2. Write code that reveals its model.

Use clear names and straightforward control flow. Make meaningful state, invariants, dependencies, and data flow understandable. Separate domain policy from external details where this improves understanding and change; introduce abstractions to serve real boundaries, not to satisfy a pattern.

## 3. Prefer clean integration to accumulated workarounds.

Assess whether a change fits the existing model, and propose bounded refactors when they resolve a concrete correctness or maintenance problem. Remove superseded paths once they are no longer needed by supported consumers. Do not make unrelated cleanup a prerequisite.

## 4. Reuse suitable capabilities before building alternatives.

Use existing codebase, platform, and dependency capabilities when they meet the need cleanly. Do not recreate an available mechanism without a concrete reason, or force reuse where the behavior does not fit. Judge dependencies and wrappers by the complexity they remove and introduce.

## 5. Make failure behavior explicit.

Keep failure distinguishable from valid results. Make error reports identify what failed and why, when known. Recover or fall back only when the resulting behavior has a defined meaning and still satisfies the relevant contract. Do not conceal errors behind defaults or apparent success.

## 6. Do not invent defensive requirements.

Base compatibility, validation, security, and recovery on real consumers, established contracts, explicit trust assumptions, and grounded risks. Follow the project’s established stance on defensive development and testing. When none is defined, implementing the agreed behavior and verifying normal operation and relevant edge cases with proportionate checks is sufficient. Broader defenses and coverage need an explicit requirement or a concrete, project-specific risk; surface that risk rather than silently expanding scope.

## 7. Verify behavior and contracts.

Verify agreed outcomes and relevant failure cases using checks appropriate to the change. Each added test or validator should protect an identifiable requirement, real consumer contract, destructive operation, or demonstrated failure.

A test should detect a meaningful violation of behavior or a contract while remaining valid through changes that preserve them. Assert relevant relationships, invariants, and outcomes. Check exact wording, structure, counts, coordinates, or tuning values when those details are themselves requirements or consumer contracts. Otherwise, let them vary and check the semantics they serve. For example, verify that text preserves its configured size rather than pinning the test to today's size.

Keep test arrangements under the test's control when incidental changes to an authored scene or dataset would otherwise break it. When that authored content is itself the requirement or consumed contract, verify the relevant content directly. Preserve checks for meaningful defects when simplifying a suite.
