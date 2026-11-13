# unit-testing-lab — ENGG*4450 Lab 8 & 9: Software Testing

A Maven project with a `Calculator` class, JUnit 5 unit tests, and JaCoCo
code coverage reporting.

## Run it (GitHub Codespaces or any machine with Java 17 + Maven)

```bash
mvn clean test
```

Expected output: **Tests run: 5, Failures: 0, Errors: 0, Skipped: 0 — BUILD SUCCESS.**

The JaCoCo coverage report is generated at `target/site/jacoco/index.html`
(green lines = covered by tests).

## What is in here

- `pom.xml` — JUnit Jupiter 5.9.2 (test scope), maven-surefire-plugin 3.2.5,
  jacoco-maven-plugin 0.8.9 (prepare-agent + report in the test phase)
- `src/main/java/com/example/Calculator.java` — `add`, `subtract`,
  `multiply`, `divide` (divide-by-zero throws `IllegalArgumentException`)
- `src/test/java/com/example/CalculatorTest.java` — 5 tests, including
  `testDivideByZero` (`assertThrows`)

## Coverage (measured with JaCoCo 0.8.9)

| Stage | Tests | Instructions | Lines | Methods | Branches |
|---|---|---|---|---|---|
| add/subtract only | 2 | 11/11 (100%) | 3/3 | 3/3 | — |
| multiply/divide added, no tests yet | 2 | 11/26 (42%) | 3/7 | 3/5 | 0/2 |
| tests added for the new methods | 5 | 26/26 (100%) | 7/7 | 5/5 | 2/2 |

Adding the two new methods without tests dropped coverage to 42%; adding
the three new tests brought it back to 100% on every counter.
