# quiqui-questions

Sample question files for [QuiQui](https://github.com/albrechtje/quiqui), a live audience response tool for university lectures.

## Structure

Each `.yaml` file in this repo represents one lecture's questions. Point QuiQui at this repo URL and select a file to load its questions.

## Question format

Each question has a `type` of either `single` (one answer) or `multiple` (one or more answers), a list of `answers`, and an optional `correct` field for the teacher's reference — it is never shown to students.

```yaml
- question: "What is the result of 7 // 2 in Python?"
  type: single
  answers:
    - "3.5"
    - "3"
    - "4"
    - "2"
  correct: "B — // is floor division. 7 / 2 = 3.5, floored to 3."
```

For `multiple` choice, `correct` lists the correct option letters:

```yaml
- question: "Which of these are valid Python data types?"
  type: multiple
  answers:
    - "int"
    - "float"
    - "char"
    - "str"
    - "bool"
  correct: "A, B, D, E — Python has no char type."
```

## config.yaml

The optional `config.yaml` file at the root of the repo configures the session:

```yaml
session_url: python101
title: Python 101
```

- **session_url** — a stable, human-readable identifier for the student join URL (e.g. `/join/python101`). If omitted, QuiQui generates a random short ID each time a question is activated. Using a fixed `session_url` means students can stay on the same URL across multiple questions in a lecture.
- **title** — optional display name shown in the header and browser tab of both the teacher and student views, formatted as `QuiQui: <title>`.
