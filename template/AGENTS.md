# AGENTS.md

IETF Internet-Drafts built with
[i-d-template](https://github.com/martinthomson/i-d-template).
Tooling docs: `lib/doc/` (`FEATURES.md`, `SUBMITTING.md`).

## Commands

- `make`: build txt/html and lint. Run after completing a batch of draft edits,
  before handing back or committing.
- `make fix-lint`: fix trailing whitespace and missing final newlines.
- `make spellcheck`, `make idnits`: optional, before a submission.
- `make diff`: rfcdiff against the last published version (`diff-*.html`).
- No network? Add `DISABLE_FETCHING=true`.

Git hooks check commits (build + lint) and draft tag pushes. Fix what they
report; never pass `--no-verify` unless the user asks.

## Editing drafts

- Edit the authored `draft-*.md`, `.org`, or `.xml` source; never edit generated
  outputs. Generated `.txt`, `.html`, and `.xml` files must not be committed
  (a newly added draft's `.xml` is not gitignored until `make update-files`).
- Each draft must contain its own name as `draft-<name>-latest`. Lint fails otherwise.

## Do not

- Create or push `draft-*-NN` tags. Pushing one submits the draft to the
  IETF datatracker. Leave submission to the user.
- Edit `lib/`. It's the toolchain, possibly a symlink shared with other repos;
  use `make update` when a toolchain update is requested.
- Hand-edit generated `README.md`.
- Edit `.github/workflows/` unless asked.
