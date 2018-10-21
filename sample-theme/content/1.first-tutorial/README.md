# Challenge file structure

Challenges are formatted as [Front-Matter](https://jekyllrb.com/docs/front-matter/).

```
---
n: ? # number of exercises (not auto-calculated yet)
---

Challenge body. Format is challenge-specific

  This paragraph will appear only on the Result tab.
  It can be used almost anywhere.

  --
  This paragraph will appear only the Initial tab.
  It can be used almost anywhere.

Beware of traling whitespace and 2+ consequent empty lines.
The parser is very strict at the moment.
```

## Types of challenges

#### Interactive

* `qzn` – multi-option quiz
* `qz1` – mono-option quiz
* `gru` – unsorted grouping / classification
* `gro` – sorted grouping / sorting

#### Non-interactive

* `tsk` – task
* `ref` – refactoring

At this moment, the only visible difference between non-interactive challenges will be a tabulator
caption. In the engine they all pass through a single `task-like` parsing branch.

## Formats of challenge bodies

Challenge/exercise separation were introduced after we've settled on some key terms. So the current terminology
may be a bit confusing. `quiz1` is a **challenge** which **exercises** are also quizzes (of the same type).
In the future, we're going to make this distinction more clean somehow.

#### Quiz1

```
Some motivational paragraph(s).

How to do something?

( ) Wrong answer #1
(x) Correct answer
( ) Wrong answer #2
( ) None of the above (sometimes IS the correct choice)

How to do something else?

( ) Wrong answer #1
(x) Correct answer
( ) Wrong answer #2
( ) None of the above (sometimes IS the correct choice)
```

Only one `(x)` can be used per exercise.

#### QuizN

Like the above, only with `[ ] / [x]` bullets.

```
[ ] Wrong answer #1
[x] Correct answer
[ ] Wrong answer #2
```

#### GroupU

```
Some motivational paragraph(s).

How to do something?

[Unmatched]
- Unused Tag
[Dock #1]
- Used Tag #1
- Used Tag #2
[Dock #2]
- Used Tag #3
- Used Tag #4

How to do something else?

[Unmatched]
[Dock #1]
- Used Tag #1
- Used Tag #2
[Dock #2]
```

The first (initial) dock may have any name, though by convention it's usually called `Unmatched`.

#### GroupO

Like the above, only with `1. Foo`-like options.

```
[Unsorted]
[Dock #1]
1. Used Tag #1
2. Used Tag #2
[Dock #2]
1. Used Tag #3
2. Used Tag #4
```

The first (initial) dock may have any name, though by convention it's usually called `Unsorted`.
The second dock may be called `Sorted` if it's the only dock except the initial.

#### Task-like

```
Some motivational paragraph(s).

\`\`\`langcode
Some code snippet
\`\`\`

How to do something?

\`\`\`[langcode]
This code will get INITIAL badge
\`\`\`

\`\`\`[langcode]
This code will get SOLUTION badge
\`\`\`

How to do something else?

... same as above
```

All task-like challenges have the same structure.
