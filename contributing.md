# Contribution Guidelines

Please read the [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you agree to uphold it.

## Contents

- [Scope](#scope)
- [Adding or updating entries](#adding-or-updating-entries)
  - [Tables](#tables)
  - [README hub](#readme-hub)
- [Quality bar](#quality-bar)
- [Lint](#lint)
- [Pull requests](#pull-requests)

## Scope

This list is a **curation** of high-quality, MCP-focused security material: threats, defenses, tooling, labs, research, and learning resources. Prefer items you can personally recommend or that have clear community value.

## Adding or updating entries

1. Open the Markdown file that fits the resource (see [README.md](README.md) **Contents**).
2. Add **one row** per tool, talk, course, or reference unless the section author explicitly groups items.
3. Use **objective** summaries: start with an uppercase letter and end with a period where the cell is a full sentence. Avoid marketing taglines.
4. Prefer **primary links** (official docs, canonical repo, or publisher page). Verify links resolve before opening a pull request.
5. For intentionally vulnerable labs or offensive tooling, keep or add **safety notes** (isolated environments, no production use).
6. Do **not** add a license section to [README.md](README.md); licensing is expressed in [LICENSE](LICENSE) only.

### Tables

Match the column headers and style of the surrounding table. Keep wording concise so rows stay scannable.

### README hub

Changes that add or rename topic pages must update [README.md](README.md) **Contents** with a single flat list entry in the form `- [Title](file.md) - Description ending with a period.`

## Quality bar

- Skip unmaintained, archived, or undocumented projects unless you isolate them under an explicitly labeled subsection agreed with maintainers.
- Fix spelling and grammar in the lines you touch.
- Avoid hard-wrapping prose in the middle of sentences (soft-wrap in your editor instead).

## Lint

Before submitting, run `npx awesome-lint` from the repository root and fix reported issues on [README.md](README.md). For documented false positives, use the inline comments described in the [awesome-lint readme](https://github.com/sindresorhus/awesome-lint/blob/main/readme.md#special-comments).

If you see `Awesome list must reside in a valid git repository`, ensure the current branch has a Git remote configured (for example `git config branch.<your-branch>.remote origin`) or run `npx awesome-lint https://github.com/<org>/<repo>` against the GitHub URL after your changes are pushed. Pull requests run lint in CI as well.

## Pull requests

- Describe what you added or changed and why it belongs in this list.
- Keep commits focused; unrelated drive-by edits increase review time.

If a maintainer asks for edits, update your pull request branch accordingly. Guidance on amending PRs: [RichardLitt/knowledge — amending a PR](https://github.com/RichardLitt/knowledge/blob/master/github/amending-a-commit-guide.md).
