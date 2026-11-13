# Factorial Calculator — Java & Maven CI

A small Java project that calculates factorial values and demonstrates a basic automated build-and-test workflow with Maven and GitHub Actions.

## Implementation

The core method is `Factorial.calculate(int n)`:

- Returns `1` for zero.
- Multiplies the integers from 2 through `n` for positive inputs.
- Throws `IllegalArgumentException` for negative inputs.

The implementation returns a Java `long`. Factorials grow quickly, so values beyond the range of `long` will overflow; this project does not currently implement arbitrary-precision arithmetic.

## Tests

JUnit 5 tests cover:

- Factorial of zero
- Factorial of five
- Factorial of ten
- Negative input rejection

## Technology

- Java 21
- Maven
- JUnit Jupiter 5
- GitHub Actions

## Run locally

### Prerequisites

- JDK 21
- Apache Maven

Clone the repository:

```bash
git clone https://github.com/padmanaban-mu/factorial-cicd-java.git
cd factorial-cicd-java
```

Run the tests and package the project:

```bash
mvn test
mvn package
```

## Continuous integration

The workflow at `.github/workflows/ci.yml` runs on pushes and pull requests targeting `main`. It checks out the repository, configures Temurin Java 21, runs `mvn test`, packages the project, and uploads the generated JAR as a workflow artifact.

## Project layout

```text
.
├── .github/
│   └── workflows/
│       └── ci.yml
├── pom.xml
└── src/
    ├── main/java/Factorial.java
    └── test/java/FactorialTest.java
```

## Possible extensions

- Use `BigInteger` to support larger factorials.
- Add boundary and overflow-related tests.
- Add a command-line interface.
- Add static analysis and code coverage to CI.

## License

No license file was identified during this documentation update. Check licensing before reuse or redistribution.
