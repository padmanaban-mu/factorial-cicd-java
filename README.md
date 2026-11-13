# Factorial Calculator

A small Java project I used to practise writing unit tests and setting up a basic CI workflow with Maven and GitHub Actions.

The application contains a factorial calculation method and JUnit tests for its expected behaviour.

## Implementation

The method `Factorial.calculate(int n)`:

- Returns `1` when the input is `0`.
- Calculates the product of the integers from `1` through `n` for positive inputs.
- Throws `IllegalArgumentException` for negative inputs.

The return type is `long`. This is enough for the test cases in this project, but large factorials exceed the range of `long` and will overflow. Arbitrary-precision support with `BigInteger` has not been added.

## Tests

JUnit 5 tests cover:

- `0!`
- `5!`
- `10!`
- Negative input

## Tools

- Java 21
- Maven
- JUnit Jupiter 5
- GitHub Actions

## Run it

Install JDK 21 and Maven, then clone the repository:

```bash
git clone https://github.com/padmanaban-mu/factorial-cicd-java.git
cd factorial-cicd-java
```

Run the tests:

```bash
mvn test
```

Build the project:

```bash
mvn package
```

## GitHub Actions

The workflow in `.github/workflows/ci.yml` runs for pushes and pull requests targeting `main`. It sets up Temurin Java 21, runs the Maven tests and package build, and uploads the generated JAR as a workflow artifact.

## Project structure

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

## Ideas to extend it

- Use `BigInteger` for factorials larger than the `long` range.
- Add tests around the largest supported input and overflow behaviour.
- Add a small command-line interface.

## License

No license file is currently present in the repository. Add one if you want to define how others may use or distribute the project.
