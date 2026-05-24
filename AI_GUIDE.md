# NetivLang AI Authoring Guide

This document defines how AI agents should read, write, edit, and validate NetivLang source files.

## Prime Rule

Do not invent syntax.

If the syntax is not defined in `LANGUAGE_GUIDE.md`, mark the area as `TODO` or ask for a language decision.

## Required Source Shape

Every canonical NetivLang source file must use:

```netiv
<Netiv="filename">
○|
  □|
    <meta>{};

    <edges>{};

    <book>{};
  |■
|●
```

## AI Editing Rules

1. Preserve the `<meta>`, `<edges>`, `<book>` order.
2. Preserve anthology and bookend delimiters.
3. Do not remove graph edges unless explicitly instructed.
4. Do not add comments inside `<book>`.
5. Use `°` only for reserved language words.
6. Use `•` for user-defined identifiers.
7. End every executable unit with `;`.
8. Prefer small functions.
9. Use methods for orchestration.
10. Use functions for low-level operations.
11. Do not silently change canonical formatting.
12. Do not create alternate export formats.
13. Do not assume NetivLang behaves like Rust, JavaScript, Python, C, or Haskell unless the guide explicitly says so.

## When Unsure

When unsure, AI agents should produce one of the following:

```netiv
°todo {
  reason: "Undefined syntax decision required"
};
```

or leave a structured note in `<meta>` or `<edges>`, not inside executable `<book>` code.

## Deterministic Outputs

AI agents must respect canonical output locations:

- File and database lists: `logs\list`
- Graph exports: `logs\graph`
- Metadata exports: `logs\meta`
- Project database: `db\netiv.db`

Do not create alternate output folders or format variants without a language decision.
