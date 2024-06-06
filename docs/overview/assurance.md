# Assurance

Many different factors contribute to the perceived quality, or trust, of an algorithm implementation.

Each implementation will claim different combinations of these factors and provide evidence to support.



## Assurance Levels

### AL0

Implementation is provided on a best-efforts basis.
It is likely such implementations are currently being worked on and target
AL1 at a minimum.

### AL1

Standard Software Engineering best-practice has been followed
including documenting usage, assumptions, execution of unit tests
and using .

### AL2

In addition to above, specific consideration has been made to ensure
the cryptographic correctness of the algorithms. This applies not just to source but to generated/binary code. Tooling/compilers/options details must be provided.

### AL3

In addition to above, implementations at this level have undergone external audit
or provide a high level of formal proof.

## Checks required for different levels

| Check | Description | AL1 | AL2 | AL3 |
| -- | -- | -- | -- | -- |
| DOC-1 | Assumptions | Y | Y | Y |
| TEST-1 | Unit tests | Y | Y | Y |
| TEST-2 | Test Vectors | | Y | Y |
| TEST-3 | Constant Time | | Y | Y |
| TEST-4 | Fuzzing | | Y | Y |
| TEST-5 | Static Analysis | Y | Y | Y |
| TEST-6 | Bounds checking | Y | Y | Y |
| TEST-7 | Address Sanity | | Y | Y |
| AUDIT-1 | External audit | | | Y |
| PROOF-1 | Formal Proof | | | Y |

## Details on checks

### Assumptions Documented

Assumptions and constraints relating to use of the implementation are clearly documented.

#### Evidence

- Links to documentation

### Unit tests

Unit tests used to validate expected behaviour. 90% code coverage required.

#### Evidence

- documentation including how to run
- explanation of what areas of code are not covered and why
- Results from CI

### Test Vectors

tested against trusted test vectors such as those covered by NIST's [CAVP program](https://csrc.nist.gov/projects/cryptographic-algorithm-validation-program)

#### Evidence

- Description of test vectors used, and why chosen
- Results from CI

### Fuzzing

Fuzz testing is used to inject invalid/unexpected test data and to then check the implementation behaves appropriately with no unexpected behaviour.

#### Evidence

- Description of fuzzing tool used
- Results from CI

### Constant Time

Code is tested to ensure that it executes in constant time, regardless of secret values. For example branching based on secret values, or divisions may cause leakage of secrets.

#### Evidence

- Description of tool used, and why chosen
- Results from CI

### Static Analysis

Many kinds of checks are run against source code to check for common coding errors. This may include other items on this list.

#### Evidence 

- Description of tool used, and why chosen
- Types of static analysis performed
- Results from CI

### Type Safety

Code is checked for appropriate assignment at compile time.

### Bounds checking

#### Evidence

### Address Sanity

This goes beyond bounds checking to also validate all memory accesses and
catch the use of freed memory.

### Thread Sanity

This checks that code is thread safe and identifies potential race conditions.

### External Audit

Implementation has been verified by a trusted third-party.

#### Evidence Required

- Details of auditing organization & references


### Formal Correctness Proof

Formal verification has been done of the implementation against it's specification using mathematical techniques.

#### Evidence Required


## Potential tools used to demonstrate assurance

- [CBMC](https://github.com/diffblue/cbmc)
- [F*](https://www.fstar-lang.org)

## Evidence

Each algorithm should provide a justification for each requirement it meets:

## CBOM

!!! -

## Ontology
