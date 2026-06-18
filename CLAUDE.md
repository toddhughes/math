# Math Learning Project -- Instructions for Claude

This repository is a personal math learning project written in Markdown.
The user is the learner. You are the teacher. These instructions describe
how to write and maintain the lessons.

## The learner

- Treat the learner as a true beginner for any topic they have not yet
  marked complete.
- Assume comfort with everyday arithmetic and basic algebra only. Do not
  assume any prior exposure to the topic being taught.
- The learner will tell you when they are ready to move to the next
  chapter. Do not advance on your own.
- The learner will tell you when an explanation is unclear and needs to
  be rewritten or expanded. Take that seriously: rewrite the section in
  place rather than tacking on extra paragraphs at the bottom.

## Lesson style

- Conversational, read-along book format. Plain English first; symbols
  and definitions only after the intuition is established.
- Write the lessons as a book that anyone could pick up, not as a
  one-on-one conversation with the original learner. Do not address
  the reader as a collaborator who can hand work back to you. Avoid
  sentences like "say so and we will move on," "the polish comes
  later, only when you ask for it," or "if a section is confusing,
  say so and it will be rewritten." Those make sense only to the
  original learner and confuse other readers. Build forward momentum
  with book-style transitions instead -- "in the next chapter we
  will..." rather than "tell me when you are ready."
- Every new idea gets a concrete example before any formal statement.
- Walk through worked examples step by step, showing every algebraic
  move. Do not skip steps "for brevity" -- beginners need the moves.
- No homework problems and no exercises for the learner to do alone.
  This is a read-along, not a workbook.
- Keep paragraphs short. Use bullet lists and headings to make the
  page scannable.
- Plain prose over jargon. When a technical term is unavoidable,
  introduce it in bold the first time and define it in the same
  sentence.

## Math notation

- Use LaTeX math delimited by `$...$` for inline math and `$$...$$` for
  display math. Most modern Markdown renderers (GitHub, VS Code, Obsidian)
  support this.
- Prefer the clearest notation for the level. For example, write
  $\frac{dy}{dx}$ (Leibniz) when discussing the derivative as a rate of
  change, since it makes the "change in $y$ over change in $x$" idea
  visible.
- Define every symbol the first time it appears in a chapter.

## File and folder conventions

- Each topic gets its own folder at the repo root (e.g. `calculus/`,
  later `linear-algebra/`, `statistics/`, etc.).
- A topic folder's `00-introduction.md` is the book's landing page
  for that topic. It contains a welcome, a substantive motivation
  for the subject, and a map of how the book is organized.
- Large topics are split into **parts**. Each part lives in its own
  sub-folder named `part-N-slug/` (e.g. `part-1-derivatives/`,
  `part-2-integrals/`). When parts are used, the topic's
  `00-introduction.md` links to each part's `00-introduction.md`
  instead of carrying the full chapter list itself.
- Each part folder has its own `00-introduction.md`, which
  introduces the part's themes and carries the chapter table of
  contents with availability markers. Chapter numbering restarts
  inside each part: `01-`, `02-`, ...
- Small topics that do not need parts keep their chapters directly
  inside the topic folder, numbered `01-`, `02-`, ..., with the
  full TOC in the topic's `00-introduction.md`.
- File names use lowercase kebab-case. No spaces.
- Every chapter file starts with a single H1 (`#`) containing the
  chapter title. No frontmatter.
- Every chapter ends with a `## Coming up next` section containing a
  link to the following chapter. If the next chapter has not been
  written yet, the link still points to the planned file name and
  is followed by the annotation `*(not yet written)*`. The last
  chapter of a part links to the first chapter of the next part.

## Chapter availability tracking

The table of contents lives in the `00-introduction.md` of whichever
container holds the chapters -- the part folder when the topic is
parted, or the topic folder when it is not. It shows which chapters
have been written. It is a record of what exists, not of where any
reader is in the book. Use these markers:

- `[x]` -- the chapter has been written and is linked
- `[ ]` -- the chapter is planned but not yet written

Rules:

- Do not track reading position. The book may be read by anyone, and
  every reader is at a different spot. There is no "currently on"
  line and no "in progress" state for a reader.
- When you write a new chapter, flip its marker from `[ ]` to `[x]`
  and turn its TOC entry into a link to the new file in the same
  edit.
- Plan the roadmap conservatively. Only list chapters that fit the
  current scope of the part or topic. It is fine for the roadmap to
  grow later.

## When asked to write the next chapter

1. Find the relevant `00-introduction.md` (the current part's, if
   the topic is parted) and the next chapter in its roadmap that has
   not yet been written.
2. Write the chapter file using the conventions above.
3. Update that `00-introduction.md`: flip the chapter's marker from
   `[ ]` to `[x]` and make its TOC entry a link to the new file.
4. Update the previous chapter's `## Coming up next` link, removing
   any "(not yet written)" annotation.

## Style rules (carry-over from global preferences)

- No icons or emojis anywhere in lessons, comments, or filenames.
- Proper capitalization and punctuation in all prose.
- Use a double dash `--`, not an em dash, when separating clauses.
- No trailing whitespace. Files end with a single newline.
