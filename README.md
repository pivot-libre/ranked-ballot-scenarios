# Ranked Ballot Scenarios

This repository enables programmers to easily verify their implementations of election methods. The repository contains machine-readable ranked ballots, expected results, and scenario descriptions. Ballots and election results are encoded in [BFF](https://pivot-libre.github.io/bff/). Programmers should be able to use the data in this repository regardless of the language or framework they use.

## Scenario Structure
All scenarios are located in the [`scenarios`](scenarios) folder. Each scenario has its own descriptively-named folder. Each scenario folder contains a `ballots.bff` file for election input and a `description.txt` for supplying context. Each scenario folder has a `results` subfolder filed with `.bff` files. Each file contains the election results according to a particular election method. The file's name corresponds to the election method.

### Example Scenario

```
scenarios
├── my-great-election-scenario
│   ├── ballots.bff
│   ├── description.txt
│   └── results
│       ├── minmax.bff
.       ├── plurality.bff
.       └── schulze.bff
.
```

## Usage
Data in this repository can be used in automated tests. Tests can parse a scenario's `ballots.bff` file into ballot objects in memory. Tests can then pass the ballots to their election method implementation and compare their results with the associated `.bff` file in the `results` folder. If the tests fail, the scenario's `description.txt` file can be used in the test's failure message to help the programmer debug their election method implementation.

## License
[Apache 2.0](LICENSE)