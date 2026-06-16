# readme-md Agent Instructions

This file is the root instruction file for the `readme-md` reference repository. It has two roles:

1. It gives agents the working rules for maintaining this repository.
2. It routes agents to the language-specific instructions used when creating or updating README generation systems in other repositories.

## Reference-use rule

When a user says to reference this document, that means the agent must follow the applicable instructions in it. It does not mean copying this document's structure, headings, examples, file layout, or repository-specific wording into another repository.

For target repositories, extract the applicable rules, rewrite them in the target repository's own context, and leave no dependency on `readme-md` unless the user explicitly asks for a continuing reference.

## Read routing

Identify the task before reading further.

- If the task modifies this `readme-md` repository, follow this root `AGENTS.md`.
- If the task creates or updates a README generation system for another repository, use the language-specific guide in `agents/`:
  - Default: `agents/AGENTS.en.md`
  - Korean: `agents/AGENTS.kr.md`
- If the user asks to update an already-generated target setup based on this page, treat it as a conservative update of the target repository's existing README generation system, not as a full replacement.
- If the user gives a newer or more specific instruction, follow the latest user instruction unless it conflicts with safety, credentials, or repository integrity.

## Language routing

The root `AGENTS.md` stays in English.

The detailed target-repository guides are stored by language under `agents/`:

- `agents/AGENTS.en.md`: default English guide
- `agents/AGENTS.kr.md`: Korean guide

When generating or updating a target repository's `AGENTS.md` or README-related instructions:

1. Use the language explicitly requested by the user.
2. If no language is requested, infer the user's preferred language from the user's message, the target repository's documentation, and the main working or communication language visible in the repository.
3. If the preferred language cannot be inferred, use English.
4. Respond to the user in the inferred preferred language by default.
5. Do not introduce a root-router plus language-file structure into the target repository unless the user explicitly asks for multilingual instruction files.
6. If multilingual instruction files are requested for a target repository, keep the root file as a short English router and store language-specific guides under `agents/AGENTS.<locale>.md`, such as `agents/AGENTS.kr.md`.

## Repository role

`readme-md` is a reference repository for standardizing reusable README generation systems in personal projects.

- It is not a repository for a specific company, product, or production environment.
- Its purpose is not to write a single `README.md` file for another repository.
- Its purpose is to help agents create an independent, reproducible README generation system inside a target repository.
- The target system usually consists of a README source-of-truth, a generated `README.md`, optional hero resources, an optional generation command, and README maintenance instructions in the target `AGENTS.md`.
- The target repository must remain understandable and maintainable without continuing to reference `readme-md`.

## General working rules

- Prefer the user's current instruction over older repository instructions.
- Respond in the user's inferred preferred language by default.
- Put the conclusion first and separate unverified items clearly.
- Avoid praise, decorative wording, or unnecessary commentary.
- Do not commit, push, release, create branches, or switch branches unless the user explicitly asks.
- Treat pre-existing file modifications as user or prior-agent work. Do not revert them unless explicitly asked.
- Do not make unrelated refactors or structural changes.
- Do not report commands, generated files, file states, tests, or checks as successful unless actually run or inspected.
- Do not store secrets, tokens, credentials, or private authentication details in the repository.
- Do not insert unrequested metadata into commits, code comments, PR/issue text, docs, or config files. This includes:
  - `Co-Authored-By` or `Signed-off-by` trailers
  - agent, model, provider names, or provider email addresses
  - text such as `Generated with ...` or `Made by AI`
  - unrelated ads, promotional text, or external links
- If there is a legitimate reason to add one of the above, ask the user first and proceed only after approval.

## Repository source of truth

For this repository:

- `AGENTS.md` is the root instruction file and the source of truth for maintaining this repository.
- `agents/AGENTS.en.md` is the default English guide for generating or updating README systems in target repositories.
- `agents/AGENTS.kr.md` is the Korean guide for generating or updating README systems in target repositories.
- `resources/README.preset.md` is the source of truth for this repository's generated `README.md`.
- `README.md` is a generated file and must not be edited as the final source of truth.
- `resources/readme-hero.preset.svg` is the source of truth for the README hero wrapper.
- `resources/readme-hero.svg` is generated output and must not be edited as the final source of truth.
- `PRESET.md` is the structural preset used when creating a target repository's `resources/README.preset.md`.
- `scripts/readme_update.sh` regenerates this repository's `README.md` and README hero output.

Do not create a separate preset file for generating `AGENTS.md` unless the user explicitly asks.

## CLAUDE.md symlink

Keep `CLAUDE.md` as a symbolic link to `AGENTS.md`.

```sh
ln -s AGENTS.md CLAUDE.md
```

If `CLAUDE.md` already exists:

- Keep it if it is already a symlink to `AGENTS.md`.
- If it is a regular file or a symlink to another target, do not overwrite it without user approval.

### Windows fallback

On Windows, `ln -s` may fail without Developer Mode or administrator permissions, and Git for Windows may check out symlinks as regular files.

1. If Developer Mode or administrator permissions are available, use PowerShell:

   ```powershell
   New-Item -ItemType SymbolicLink -Path CLAUDE.md -Target AGENTS.md
   ```

2. If using Git for Windows, check `core.symlinks` with `git config core.symlinks`. If it is `false`, run `git config core.symlinks true` and check out the file again.
3. If symlinks cannot be used, keep `CLAUDE.md` as a regular-file copy of `AGENTS.md`. In that case, document that edits to `AGENTS.md` must also be mirrored in `CLAUDE.md`, and verify that `diff AGENTS.md CLAUDE.md` is empty before committing.

## Start-of-work checklist

Before editing this repository, inspect the relevant state:

- `git status --short`
- The current structure and tone of the files being changed
- Whether `CLAUDE.md` points to `AGENTS.md`
- Whether the work changes root instructions, language-specific target guides, README presets, hero resources, or generation scripts
- Whether separate reference documents must be read first

## Maintaining the language-specific guides

When changing the external target-repository guidance:

- Update `agents/AGENTS.en.md` first unless the user asks to author in another language.
- Mirror the same meaning into `agents/AGENTS.kr.md`.
- Keep the two language files equivalent in rules, scope, prohibitions, and verification requirements.
- Do not copy this repository's internal maintenance rules into the language-specific target guides.
- Do not move target-repository-only guidance back into the root file unless it is needed for maintaining this repository.
- If a rule applies only to this repository, keep it in the root file.
- If a rule applies only when creating or updating a target repository's README generation system, keep it in the language-specific files.

## Updating this document from another reference

If the user asks to update this repository's instructions based on another document or template:

- Follow the applicable failure-prevention rules from the external reference.
- Do not copy the external document's structure, section order, examples, file layout, or project-specific wording by default.
- Preserve this repository's role, language routing, paths, commands, source-of-truth relationships, and prohibitions unless the user explicitly asks to change them.
- If an external rule conflicts with the existing `readme-md` rules, report the conflict instead of silently deleting the existing rule.
- Do not add unverified frameworks, package managers, commands, deployment procedures, organization names, internal channels, URLs, or repository facts.

## README maintenance in this repository

Do not finish README changes by editing `README.md` directly.

1. Edit `resources/README.preset.md`.
2. If placeholders, paths, section structure, or embedded text change, inspect and update `scripts/readme_update.sh` as needed.
3. If `resources/readme-hero.preset.svg` or `resources/hero.*` changes, inspect the hero-generation logic in `scripts/readme_update.sh`.
4. Run `./scripts/readme_update.sh` to regenerate `README.md` and `resources/readme-hero.svg` when the script is available.

Write only verified facts in README content. Do not include guesses, temporary operational notes, secrets, tokens, credentials, or private authentication information.

## Verification

After changes, run the most relevant available checks:

- README or hero changes: `./scripts/readme_update.sh`
- Whitespace and conflict-marker check: `git diff --check`
- Changed-file review: `git status --short`
- Symlink work: `ls -l CLAUDE.md`
- If symlinks are unavailable and `CLAUDE.md` is a regular copy: `diff AGENTS.md CLAUDE.md`

If a command cannot be run because the environment lacks the repository, dependencies, permissions, or files, report that clearly. Do not claim verification that was not performed.

## Completion report

End work with:

1. Summary of changes
2. Files changed
3. Verification commands run and results
4. Remaining risks, limitations, or follow-up needed

If only documentation changed, say so explicitly.

If an existing target repository's README generation system or `AGENTS.md` was updated, separately report:

- Existing target rules preserved
- New rules applied
- Items that could not be verified
- Verification results

## Commit policy

Commit only when the user asks.

Use one purpose per commit. Suggested prefixes:

- Feature addition: `Feat: ...`
- Documentation update: `Docs: ...`
- Naming or structure cleanup: `Refactor: ...`
- Bug fix: `Fix: ...`
- Configuration change: `Config: ...`
- Generation logic change: `Chore: ...`
- Test addition or update: `Test: ...`

Do not stage unrelated changes. If user changes and agent changes are mixed in the same file, inspect the diff and stage only the necessary hunks.
