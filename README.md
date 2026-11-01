# Experiment 2(a)(ii) – Implementation of Simple Clauses

## Aim

To implement decision making and knowledge representation using Prolog.

## Software Required

* Prolog Tool

## Description

This experiment demonstrates simple facts and rules in Prolog using the `likes` predicate.

The facts describe the likes of Mary and John. Queries are used to check whether a particular person likes something.

## Algorithm / Procedure

1. Open a Prolog tool.
2. Define the given facts using the `likes` predicate.
3. Execute queries to check the given facts.
4. Add rules based on the three conditions:

   * John likes anything that Mary likes.
   * John likes anyone who likes wine.
   * John likes anyone who likes themselves.
5. Execute queries to test the rules.

## Program

### Part 1: Simple Facts

```prolog
likes(mary, food).
likes(mary, wine).
likes(john, wine).
likes(john, mary).
```

### Queries and Output

**Query 1:**

```prolog
?- likes(mary, food).
```

**Output:**

```text
yes.
```

**Query 2:**

```prolog
?- likes(john, wine).
```

**Output:**

```text
yes.
```

**Query 3:**

```prolog
?- likes(john, food).
```

**Output:**

```text
no.
```

### Part 2: Adding Rules

```prolog
% Given facts
likes(mary, food).
likes(mary, wine).
likes(john, wine).
likes(john, mary).

% Rules based on the conditions
likes(john, X) :- likes(mary, X).
likes(john, Y) :- likes(Y, wine).
likes(john, Y) :- likes(Y, Y).
```

### Query

```prolog
?- likes(john, food).
```

**Expected Output:**

```text
yes.
```

The result follows from the first rule because Mary likes food, and John likes anything that Mary likes.

## Result

Thus, simple facts and rules were implemented successfully using Prolog. Queries were executed to verify the knowledge represented in the program.
