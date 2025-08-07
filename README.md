**Project Title**

Knights and Knaves Puzzle Solver

---

## Overview

This project implements a solver for classical “Knights and Knaves” puzzles using propositional logic and a model-checking algorithm. Each puzzle features characters who are either knights (always truthful) or knaves (always lying). The solver encodes each puzzle’s statements into a logical knowledge base and automatically determines each character’s identity.

---

## Implementation Summary

* **logic.py** provides a framework of logical connectives (`Symbol`, `And`, `Or`, `Not`, `Implication`, etc.) and a `model_check` function to evaluate entailment.
* **puzzle.py** defines propositional symbols for each character (e.g., `AKnight`, `AKnave`, `BKnight`, etc.) and four completed knowledge bases (`knowledge0` through `knowledge3`) corresponding to Puzzles 0–3:

  * Puzzle 0: A says, “I am both a knight and a knave.”
  * Puzzle 1: A says, “We are both knaves.” B says nothing.
  * Puzzle 2: A says, “We are the same kind.” B says, “We are of different kinds.”
  * Puzzle 3: A makes an unknown one-of-two statement; B reports what A said and claims “C is a knave;” C asserts “A is a knight.”

Each knowledge base:

1. Asserts that each character is exactly one of knight or knave.
2. Encodes each spoken sentence as an implication tied to the speaker’s truthfulness.

---

## Running the Solver

With the puzzles already encoded, simply execute:

```bash
python puzzle.py
```

The script will output each character’s deduced identity. For example:

```
Puzzle 0:
  A is a knave.
Puzzle 1:
  A is a knave.
  B is a knight.
... etc.
```

---

## Results

* **Puzzle 0**: A = Knave
* **Puzzle 1**: A = Knave, B = Knight
* **Puzzle 2**: A = Knight, B = Knave
* **Puzzle 3**: A = Knight, B = Knight, C = Knave


