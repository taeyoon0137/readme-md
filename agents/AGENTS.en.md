# README Generation System Instructions

This document is the English reference for creating or updating a reusable README generation system in a target repository.

It is not a file to copy verbatim into the target repository. Rewrite the applicable rules in the target repository's own `AGENTS.md`, `resources/README.preset.md`, and README generation command so the target repository can be understood and maintained independently.

## Reference-use rule

When a user says to reference this document, that means the agent must follow the applicable instructions in it. It does not mean copying this document's structure, headings, examples, file layout, or repository-specific wording.

Apply the rules to the target repository's actual files, language, tools, and conventions. Do not leave instructions saying that future agents must continue to reference `readme-md`, this file, or the original repository unless the user explicitly requests that dependency.

## Language policy

Use the user's explicit language request first.

If the user does not specify a language, infer the target `AGENTS.md` language from:

- the user's message language
- the main language of the target repository's README and docs
- the visible working or communication language in issues, docs, comments, or contribution guidelines
- the product or project locale when it is clear from repository content

Default to English if the language cannot be inferred.

Agents should respond to the user in the inferred preferred language by default. Do not mix languages inside the target `AGENTS.md` unless the target repository already uses multilingual instructions or the user asks for multilingual output.

If the user asks for language-specific instruction files, keep the target root `AGENTS.md` as a short English router and place detailed guides under `agents/AGENTS.<locale>.md`, for example `agents/AGENTS.kr.md`. Do not introduce this multilingual routing structure without an explicit request.

## Scope

The goal is not to write only a single `README.md` file. The goal is to create or update a reproducible README generation system inside the target repository.

Limit the applied scope to README-related artifacts:

- generated `README.md`
- README source-of-truth, usually `resources/README.preset.md`
- README generation command or script when needed
- README hero source and generated hero output when a hero is used
- README maintenance instructions in the target `AGENTS.md`
- command-list integration such as `package.json`, `Makefile`, or `justfile` only when a README generation command is actually created

Do not apply this reference repository's response style, commit policy, branch policy, deployment process, local workflow, personal-project identity, or file structure as general target-repository rules.

## What not to copy

Do not add any of the following to the target repository unless the user explicitly asks:

- a sentence telling future agents to keep referencing `readme-md`
- the local path, GitHub URL, or repository name of the reference repository
- text such as `see this repository for details`
- this reference repository's README prose as the target project introduction
- this document's section order as the target `AGENTS.md` structure
- this repository's generated `resources/readme-hero.svg`
- this repository's unique hero image files such as `resources/hero.png`, `resources/hero.light.png`, or `resources/hero.dark.png`
- a single standalone `README.md` without a source-of-truth when a generation system is requested
- target code, deployment, operation, or configuration rewrites unrelated to README generation

The result must make sense after cloning only the target repository.

## Initial inspection

Before creating or updating the target README generation system, inspect the target repository.

Check at least:

- `git status --short`
- existing root and nested `AGENTS.md` files
- existing `CLAUDE.md`
- existing `README.md`
- docs, contribution guidelines, and operation notes
- package manifests and lockfiles such as `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, `Gemfile`, and their lockfiles
- config files, CI files, and script directories
- whether `package.json`, `Makefile`, `justfile`, or another command list exists
- the repository's actual language, framework, runtime, and package manager
- source-of-truth relationships between generated files and manual files
- available build, test, lint, format, and README generation commands

Do not invent technologies, commands, deployment methods, organization names, private URLs, or file paths that were not verified in the repository.

## Application order for a new target setup

When creating a README generation system in a target repository, follow this order.

1. Read target instruction files first: `AGENTS.md`, nested `AGENTS.md`, `CLAUDE.md`, README, docs, and contributing documents.
2. Before using the existing target `README.md` as input, fix the reference repository's `PRESET.md` structure as the initial skeleton for the target `resources/README.preset.md`.
3. Copy only the reference `resources/readme-hero.preset.svg` into the target repository if the hero system is used.
4. Then inspect `package.json`, lockfiles, `.nvmrc`, config files, docs, and scripts.
5. If an existing target `README.md` exists, read it only after the preset skeleton is fixed. Use it only to extract verified facts such as project role, setup commands, generated files, and modification rules.
6. Fill the fixed preset skeleton with verified target facts.
7. If automatic regeneration is needed, add a simple and reproducible generation command or script suited to the target repository.
8. If the target repository has a command list and a README generation command was created, register that command in the list.
9. Put a generated-file comment at the top of the generated `README.md`.
10. Add README maintenance rules to the target `AGENTS.md`.

Do not link back to the reference repository during this process.

## Template enforcement rules

An existing target `README.md` is a fact source only. It is not the template.

`resources/README.preset.md` must start from the reference `PRESET.md` structure, not from the target's old README. The task is to fill the preset's placeholders, sections, hero block, and generated-file comment with verified target facts.

Keep these rules:

1. Before opening the existing target `README.md` for structure decisions, set the reference `PRESET.md` structure as the target `resources/README.preset.md` draft.
2. Preserve the generated-file comment, hero block, title/description/badge area, table-of-contents and H2 anchor pattern, and plaintext tree format for the repository-structure section.
3. Fill the sections with facts confirmed from target files.
4. Do not use the old README's H2 order, table of contents, badge layout, image placement, or prose flow as the new structure.
5. If the old README structure seems preferable, stop and rewrite using the preset structure.

When the old README contains useful content, move it by meaning instead of copying its structure:

- Rewrite project introduction into the role or overview section.
- Put install, run, build, and README-generation commands into the relevant setup or scripts section only when verified.
- Discard the old table of contents and rebuild it from the final H2 sections.
- Recreate badges only when the actual stack and links are verified.
- Prioritize badges for the target project's core stack.
- If target repository version or deployment state is important, separate repository/version/status badges from technology-stack badges.
- Do not copy old hero or image placement directly. Route hero images through `resources/hero.*` and `resources/readme-hero.preset.svg`.
- Write repository structure as a `plaintext` tree code block, not as a table or prose-only description.

`PRESET.md` and `resources/readme-hero.preset.svg` are the starting skeleton. Optional sections may be removed, and necessary target-specific sections may be added, but do not redesign the hero block, generated-file comment, source-of-truth relationship, or README generation contract.

Treat the result as failed and rewrite if any of these happen:

- `resources/README.preset.md` has the same initial structure as the old target `README.md`.
- The old README's H2 order, table of contents, badge area, or image placement is preserved.
- The hero block or generated-file comment from the preset disappears.
- The repository-structure section is a table or prose instead of a `plaintext` tree.
- `resources/README.preset.md` looks like a lightly edited copy of the old README.

## Required target outputs

A target README generation system should include the following when applicable:

- `README.md` with a top comment marking it as generated output
- `resources/README.preset.md` or an equivalent README source-of-truth
- `resources/readme-hero.preset.svg` as the hero wrapper source-of-truth when a hero is used
- generated `resources/readme-hero.svg` when the hero system is used
- `scripts/readme_update.sh` or an equivalent generation command when automatic regeneration is needed
- command-list registration when the target repository has `package.json`, `Makefile`, `justfile`, or a similar command list and a README generation command was created
- documentation that README changes start from the source file, not direct editing of generated output
- README maintenance instructions in the target `AGENTS.md`

Do not leave these incomplete forms:

- only a new or overwritten `README.md`
- the old target `README.md` moved unchanged into `resources/README.preset.md`
- a README that describes generation rules but has no source-of-truth file
- a README generation command that is omitted from an existing command list
- a generic template pasted without inspecting target `AGENTS.md`, scripts, or config files
- a target README or `AGENTS.md` that cannot be understood without continuing to reference `readme-md`

## Updating an existing target setup

If the target repository already has `AGENTS.md`, `resources/README.preset.md`, a README generation script, or a generated `README.md`, treat the request as a conservative update.

Do not replace the target's existing instruction system just because this reference has a different structure.

Follow these rules:

- Preserve the existing target `AGENTS.md` language, section structure, repository role, commands, verification rules, and prohibitions as much as possible.
- Add or merge only the README generation rules needed to prevent failure.
- Keep target-specific rules more important than generic reference wording.
- If target-specific rules conflict with this reference, report the conflict and do not remove target rules without user approval.
- Merge duplicate rules when the meaning can be preserved.
- Separate commands, links, deployment steps, or generated-file relationships that could not be verified into a `needs confirmation` note instead of silently rewriting them as facts.
- Do not introduce root/language-file routing into the target repository unless the user explicitly asks for it.
- Preserve an existing README source-of-truth if it already works, unless the user explicitly asks to migrate it.
- If the target already has a README generation command, update it instead of creating a competing command.
- If the target already has generated-file comments or hero rules, align them with this reference only where the target context supports it.

After updating, run the available verification commands, such as `git diff --check`, `git status --short`, and the target README generation command if it exists.

## README rules to add to the target AGENTS.md

The target `AGENTS.md` must independently explain how to modify README files. Include the applicable version of these rules.

- `README.md` is generated output and direct edits to it are not sufficient.
- To change README content, edit `resources/README.preset.md` or the target repository's chosen README source-of-truth.
- Use the old `README.md` only as a fact source. Do not use its structure or prose flow as the template for `resources/README.preset.md`.
- Maintain the README source by filling the preset structure with verified target facts.
- If the old README structure conflicts with the preset structure, the preset structure wins unless the user explicitly asks otherwise.
- If placeholders, paths, or section structure in the README source change, update the README generation command or script at the same time.
- If automatic regeneration is needed, run `scripts/readme_update.sh` or the target repository's configured generation command after editing the source.
- If no automatic regeneration command is needed, document only the source-editing rule in the target `AGENTS.md`; do not create an unnecessary script or README scripts section.
- If the target has `package.json`, `Makefile`, `justfile`, or a similar command list and a README generation command was created, register the command there.
- If the target has several meaningful scripts, include a scripts section in README and include the README generation command when it exists.
- Do not refactor or rewrite target code, config, deployment, or operation rules only because README-related files changed.
- Write the final H1 title directly in `resources/README.preset.md`.
- Do not let a generation command overwrite the H1 title using `package.json` name, directory name, git remote, `${projectName}`, or `${displayName}` placeholders.
- Do not leave an H1 placeholder in the target `resources/README.preset.md`.
- Treat the H1 rule as an authoring rule, not something to solve only with script validation.
- Write the final one-line description directly in the centered description block. Do not leave a `${description}` placeholder, and do not let the script generate or overwrite it.
- Write final hero image `alt` text directly in the README source. Do not leave placeholders such as `${projectName} hero image`, and do not let the script generate or overwrite it.
- Write the repository-structure section as a `plaintext` code-block tree, not as an arbitrary table.
- If a table of contents exists, update it whenever H2 sections are added, removed, or renamed.
- Keep internal links, badge links, and image links relative to the target repository or as verified public URLs.
- Add badges only for verified core technologies, package managers, deployment state, or repository version information.
- Prioritize badges that help readers quickly understand the project, such as runtime, language, framework, package manager, or documentation format.
- If repository version or deployment status matters, split badges into two lines: repository/version/status first, technology stack second.
- When adding or removing badges, update both the README source and the generated README.
- Do not redesign `resources/readme-hero.preset.svg`.
- From the reference repository, copy only `resources/readme-hero.preset.svg` for hero support. Do not copy generated hero output or unique hero image files.
- The README generation command must create `resources/readme-hero.svg` from `resources/readme-hero.preset.svg` and embed only existing `hero.png`, `hero.jpg`, `hero.light.*`, or `hero.dark.*` images as base64 data URIs.
- Replace fallback text `readme-md` inside generated `resources/readme-hero.svg` with the target repository name.
- Add a custom hero as `resources/hero.png`.
- Add mode-specific heroes as `resources/hero.light.png` and `resources/hero.dark.png` when needed.
- Start H2 headings with one meaningful emoji when it helps section scanning.
- Adjust tags, badges, table of contents, section names, section order, and section inclusion to the target repository's actual needs.
- Do not record secrets, tokens, credentials, or private internal URLs in README or the README source.
- Do not claim README generation commands, links, badges, or images were verified unless actually checked.
- Write only verified facts in README and do not leave dependency text pointing back to the external template repository.

## Repository-type branching

Use repository facts to decide which README sections and metadata are appropriate.

- If `package.json` exists, `name`, `version`, `packageManager`, `scripts`, and `repository` may be used as README metadata after verification.
- If `package.json` does not exist, do not invent package name, package version, or package-manager badges.
- For a general Git repository, directory name and git remote may be used as basic metadata after verification.
- For documentation-only repositories, prioritize document role, editing principles, and modification procedure over install and build steps.
- For monorepos or workspaces, separate the role of the root README from subproject READMEs.
- Do not add `package.json` to the reference-style README system unless the target repository actually needs one for its own tooling.

## README.preset.md structure

Create the target `resources/README.preset.md` from the reference `PRESET.md` structure first, then fill it with verified target repository facts.

`PRESET.md` is a structural preset for agents. In the target repository, the actual source file is `resources/README.preset.md` or an equivalent source-of-truth chosen for the target.

The preset is the starting skeleton, not just a loose example. Remove optional sections that do not fit the target repository and add needed sections, but do not change the source-of-truth model merely to follow the old README.

Do not put `README modification method` as a main H2 section unless the target repository explicitly needs it as user-facing documentation. Prefer the generated-file comment and target `AGENTS.md` maintenance instructions.

Do not carry over items meaningful only to the reference repository. For example, `./scripts/readme_update.sh` is the core command in the reference repository, but in a target repository it is only used if automatic README regeneration is needed.

If the target repository has multiple meaningful scripts, create a README scripts section. If there are no scripts worth exposing or no separate generation command is needed, omit that section and table-of-contents item.

The repository-structure section must use a `plaintext` code-block tree. Delete items that do not exist in the target repository and keep only important source files, generated outputs, entry points, and configuration files.

## README section guidance

Use these as a default skeleton and adjust to the target repository.

- Hero and title: final H1, one-line description, repository/version/status badges, and technology-stack badges.
- Role: what the repository does and does not do.
- Getting started: runtime, package manager, install, run, and build commands when verified.
- Main workflow: generation, build, deployment, or operational reflection flow when relevant.
- Repository structure: important directories and generated files as a `plaintext` tree.
- Scripts: actual executable commands. Omit if there is nothing useful to expose.
- Modification method: source file and generation command, usually in comments and target `AGENTS.md`, not as a main user-facing H2.
- Collaboration notes: `AGENTS.md`, generated-file principles, and commit/deployment cautions when relevant to the target repository.

## Hero image rules

When using the hero system:

- Copy `resources/readme-hero.preset.svg` from the reference repository as the target hero wrapper source.
- Do not copy reference generated hero output or unique hero image files.
- Do not redesign the wrapper or create an unrelated SVG/HTML/CSS hero system.
- The README generation command reads `resources/readme-hero.preset.svg` and creates `resources/readme-hero.svg`.
- Replace fallback text `readme-md` with the target repository name during generation.
- Embed only actually existing target files as base64 data URIs:
  - `resources/hero.png`
  - `resources/hero.jpg`
  - `resources/hero.light.png`
  - `resources/hero.light.jpg`
  - `resources/hero.dark.png`
  - `resources/hero.dark.jpg`
- Remove `<image>` tags for missing hero image files from the generated SVG.
- Tell users to add `resources/hero.png` for a custom default hero.
- Tell users to add `resources/hero.light.png` and `resources/hero.dark.png` for mode-specific heroes.
- In the preset image order, `hero.light.*` and `hero.dark.*` draw over `hero.png` or `hero.jpg` in their modes. If a mode-specific image should override only one mode, keep a default `hero.png` or `hero.jpg` for the other mode.
- `.jpg` files are allowed when present, but default guidance should prefer `.png` names.
- The README source and generated README should reference `resources/readme-hero.svg` and leave comments explaining that custom images are added through `hero.*` files followed by the generation command.

## Writing standards

README should help a new contributor understand the repository and start work quickly.

- Separate what the project does from what it does not do.
- Start H2 headings with one meaningful emoji when it improves scanning.
- Adjust tags, badges, table of contents, section names, section order, and section inclusion to the repository.
- Include core technology badges when verified.
- Split repository/version/status badges from technology-stack badges if repository version or deployment status is important.
- For small documentation repositories, keep the table of contents short or omit it.
- For libraries, apps, or operation repositories, split usage, API, deployment, and operation sections when relevant.
- Load README hero through generated `resources/readme-hero.svg`; do not manually redesign `resources/readme-hero.preset.svg`.
- Write final one-line description and hero `alt` text in `resources/README.preset.md` without placeholders.
- Add dark/light hero files only when needed.
- Keep fallback text in `resources/readme-hero.svg` as the target repository name behind the image layer.
- Use fallback background color `#00224411` in light mode and `#000C18CE` in dark mode.
- Write install, run, build, and README generation commands only when actual scripts or commands are verified.
- Distinguish generated files from manually edited source files.
- Use a tree code block, not a table, for repository structure.
- If operation or deployment procedures exist, state actual reflection points and verification steps.
- Use external links only when necessary and avoid links likely to break.
- Use company names, product names, and internal terms only when needed in the target repository.
- Do not mix repository-specific facts with generic rules.
- If document source and generation script placeholders, paths, or embedded text must stay in sync manually, update both.

## Verification

After applying the system in a target repository, run the available relevant checks.

Prefer:

- target README generation command, if created or changed
- `git diff --check`
- `git status --short`
- target-specific checks already documented in the repository when they are relevant

If a command is unavailable or cannot be run because of environment setup, permissions, missing dependencies, or missing files, report that clearly. Do not claim the command passed.

## Completion report

Report concisely:

1. Summary of changes
2. Changed files
3. Verification commands run and their results
4. Remaining risks, limitations, or follow-up needed

If only documentation changed, say so explicitly.

When updating an existing target `AGENTS.md` or README generation system, separately report:

- existing target rules preserved
- new rules applied
- conflicts or items needing confirmation
- verification results
