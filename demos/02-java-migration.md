# 2. Java 8 to Java 17 migration with proof

**What it shows:** Devin records tests and a benchmark on Java 8, replaces APIs removed from the JDK, gets the suite green on Java 17, and puts before/after numbers in the PR.

**Starter repo:** [devin-demo-java-migration](https://github.com/thequantexplorer/devin-demo-java-migration)

**Needs:** GitHub only (Devin installs JDK 8 and 17 itself)

Setup steps are in the starter's [DEVIN_DEMO.md](https://github.com/thequantexplorer/devin-demo-java-migration/blob/main/DEVIN_DEMO.md).

## Prompt

```text
Migrate https://github.com/<you>/devin-demo-java-migration from Java 8 to Java 17.

Before touching anything, capture a baseline on Java 8: full `mvn test` results and the invoice benchmark (see README). Then plan the migration, replace removed/internal APIs (sun.misc.BASE64*, javax.xml.bind, Joda-Time where sensible), bump JUnit and the compiler target, and get the suite green on Java 17.

Deliver a PR with a before/after report in the description: test counts per JDK, benchmark elapsed_ms per JDK (same input size), every API replaced and why, and any behavioral risks. If Maven Central rate-limits you, use the GCS mirror https://maven-central.storage-download.googleapis.com/maven2/.
```

## Presenter notes (spoilers)

What Devin should find, so you can narrate it. Keep this out of the starter repo so Devin finds it on its own.

- On Java 8, 12 tests pass and `BillingRun 200000` takes roughly 0.5 s. On Java 17 the build fails at compile time on `sun.misc.BASE64Encoder`.
- Expect `java.util.Base64`, Jakarta JAXB (or no XML binding at all), `java.time` in place of Joda/`Date`, `RoundingMode`, and JUnit 5, with a before/after table in the PR.
