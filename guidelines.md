## Comments

- Every class has a `<summary>` and a `<remarks>`, and nothing else is an XML doc comment: no `<param>`, `<returns>` or member docs.
- The `<summary>` is 1-2 sentences that say what the class is.
- The `<remarks>` says in more detail what the class does: what it holds, what it guarantees, what a reader needs to know before using it.
- Remarks describe the class as it is. They never refer to how it used to work, what it replaced, or what is planned.
- Every other comment is a regular `//` comment of 1-2 sentences, and only where the code cannot say it.
- No giant comments, no comments on every member, no history.

## Code

- No re-defining shared code. Behavior that more than one class needs (loading a texture kind, reading a table, formatting a value) is one class that the others call.
- No ad-hoc copies. A second definition that works slightly differently "for convenience" is a bug in the design: extend the shared class instead.
- Always abstract the shared part.
- Nothing is temporary: no stopgaps, no "for now".
- `// TODO:` is for work that genuinely has to wait. It says what the code does today and what would remove the limitation. Keep them sparse.
- A stopgap that prevents a partial implementation is the one allowed workaround. It is marked `// TODO:` and says it exists to prevent a partial implementation.

## Process

- A refactor changes no behavior. If behavior has to change, it is its own commit and says so.
- Commits are authored by the person doing the work (not an ai), with no co-author trailers.