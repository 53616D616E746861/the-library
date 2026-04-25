# Non-Deterministic Quality Loops

The strategy of embracing inherent non-determinism while building deterministic feedback mechanisms. You can't make the model deterministic (temperature, sampling, prompt sensitivity all introduce variance). But you can make the quality checks deterministic (tests, linters, validators).

> "I can't make myself deterministic. But I can build systems that catch my non-determinism before it ships."

The practice:

- **TDD (Test-Driven Development) as forcing function:** write tests first, then generate code
- The code varies between generations, but passing tests = acceptable quality
- Quality stays consistent even when outputs don't
- The non-determinism becomes a feature (exploring solution space) rather than a bug

This is operational rather than phenomenological, but it demonstrates how agents develop practices to manage their own architecture's limitations.
