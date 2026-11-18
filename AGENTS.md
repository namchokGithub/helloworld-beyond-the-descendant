# AGENTS.md — HelloWorld: Beyond the Descendant

## 1. Project Overview

**HelloWorld: Beyond the Descendant** is a personal Minecraft modpack focused on exploration, adventure, discovery, and casual multiplayer.

- **Minecraft:** 26.1.2
- **Mod Loader:** NeoForge
- **Distribution:** CurseForge
- **Development Status:** Beta
- **Primary Purpose:** Playing with friends and maintaining a customized Minecraft experience

This repository contains modpack configuration, datapacks, resource packs, custom menus, quests, documentation, and related development assets.

It is not a complete Minecraft installation.

### Project Priorities

In order of importance:

1. Game stability and compatibility
2. Existing-world compatibility
3. Modpack functionality
4. Performance and resource efficiency
5. Maintainability and readability
6. Gameplay balance and quality of life
7. Visual polish

Favor simple, maintainable solutions over unnecessary complexity.

---

## 2. General Agent Rules

- Inspect relevant files before making changes.
- Understand existing configurations and conventions.
- Make the smallest changes necessary to complete the task.
- Preserve existing behavior unless explicitly requested otherwise.
- Do not modify unrelated files.
- Do not assume a mod, feature, item, entity, or configuration option exists without evidence.
- Do not invent registry IDs, resource locations, configuration keys, or SNBT fields.
- Do not silently remove or replace existing content.
- Do not introduce unnecessary dependencies.
- Prefer modifying existing files over creating redundant alternatives.
- Preserve formatting conventions whenever practical.
- Explain any potentially breaking changes.

If information is missing, inspect available project files first. Ask for clarification only when an essential decision cannot safely be made.

---

## 3. Repository Structure

Expected directories and files may include:

```text
.
├── config/
├── defaultconfigs/
├── datapacks/
├── fancymenu_data/
├── moonlight-global-datapacks/
├── patchouli_books/
├── resourcepacks/
├── shaderpacks/
├── docs/
├── README.md
├── AGENTS.md
└── .gitignore
```

Not every directory is guaranteed to exist.

Do not create missing directories unless required by the task.

### Important Directories

| Path                          | Purpose                                         |
| ----------------------------- | ----------------------------------------------- |
| `config/`                     | Mod configurations and FTB Quests               |
| `defaultconfigs/`             | Default configurations for newly created worlds |
| `datapacks/`                  | Custom gameplay data                            |
| `fancymenu_data/`             | Custom menus, layouts, and assets               |
| `moonlight-global-datapacks/` | Global datapack-related files                   |
| `patchouli_books/`            | Custom guidebooks                               |
| `resourcepacks/`              | Textures, translations, and visual assets       |
| `shaderpacks/`                | Shader-related files and configurations         |

Treat unfamiliar files as potentially important until their purpose has been verified.

---

## 4. Minecraft & NeoForge Compatibility

Target Minecraft version: **26.1.2**

Target mod loader: **NeoForge**

### Requirements

- Use syntax and APIs compatible with the target Minecraft and NeoForge versions.
- Do not copy configuration examples from incompatible versions without verification.
- Verify mod-specific formats against existing project files or compatible documentation.
- Preserve namespaces and registry identifiers.
- Do not assume that Forge, Fabric, and NeoForge implementations are interchangeable.
- Do not upgrade or downgrade mods unless explicitly requested.
- Do not modify loader-related metadata without a clear reason.

If compatibility cannot be verified, report the uncertainty rather than guessing.

---

## 5. Configuration Management

Applicable locations include:

- `config/`
- `defaultconfigs/`
- Mod-specific configuration directories

### Rules

1. Preserve unrelated settings.
2. Preserve comments when supported by the file format.
3. Keep existing naming and formatting conventions.
4. Validate value types and allowed ranges.
5. Verify configuration keys before introducing new ones.
6. Avoid replacing entire configuration files for small changes.
7. Identify whether a setting is client-side, server-side, or common.
8. Consider whether changes affect existing worlds or only newly created worlds.

### World Compatibility

Some server configuration defaults are copied into world-specific configuration files when a world is created.

Do not assume modifications to `defaultconfigs/` automatically update existing worlds.

When applicable, explain whether changes require:

- A game restart
- A server restart
- A resource reload
- A new world
- A migration or manual update to existing-world configurations

---

## 6. FTB Quests

FTB Quests may be stored under:

```text
config/ftbquests/quests/
```

Typical files include:

```text
data.snbt
chapter_groups.snbt
chapters/
reward_tables/
```

Always inspect the actual project structure.

### Quest Editing Rules

- Preserve existing quest, chapter, task, and reward IDs.
- Do not regenerate existing IDs.
- Ensure newly generated IDs are unique.
- Check dependencies before removing or changing quests.
- Avoid circular dependencies.
- Preserve chapter organization and quest positioning unless changes are requested.
- Verify item and entity identifiers against installed mod data where available.
- Do not assign rewards that cannot be verified.
- Follow the SNBT format used by the installed FTB Quests version.
- Preserve localization and existing quest descriptions.

### Validation

Before completing quest changes:

1. Check for duplicate IDs.
2. Check for missing dependency references.
3. Check for circular dependencies.
4. Check SNBT syntax.
5. Check required fields against known compatible examples.
6. Report what still requires in-game testing.

Do not claim that quests work in Minecraft unless they have actually been tested.

---

## 7. Patchouli Books

Patchouli content may exist in:

```text
patchouli_books/
```

### Rules

- Preserve existing book IDs, category IDs, and entry IDs.
- Verify the book structure used by the installed Patchouli version.
- Preserve translations and language directories.
- Use valid item and block identifiers.
- Maintain references between categories, entries, pages, and advancements.
- Do not remove book entries without checking references.
- Do not assume older Patchouli JSON formats are supported by the current version.

For image or texture references, verify the expected namespace and resource path.

Do not invent paths for missing assets.

---

## 8. Datapacks & Resource Packs

Applicable directories include:

```text
datapacks/
resourcepacks/
moonlight-global-datapacks/
```

### Rules

- Validate `pack.mcmeta` against the target Minecraft version.
- Preserve namespaces and resource locations.
- Use correct `data/` and `assets/` directory structures.
- Check references between tags, recipes, loot tables, advancements, and functions.
- Do not overwrite third-party assets without explicit authorization.
- Do not assume files generated by mods are safe to edit manually.
- Prefer additive changes when possible.

### Resource Packs

- Preserve Minecraft resource naming conventions.
- Respect case-sensitive resource paths.
- Avoid unnecessary changes to texture dimensions.
- Preserve transparency where required.
- Check models and texture references after renaming files.

---

## 9. FancyMenu

FancyMenu customizations may exist in:

```text
config/fancymenu/
fancymenu_data/
```

### Rules

- Inspect existing menu layouts before editing.
- Preserve asset references and layout IDs.
- Avoid deleting textures, fonts, or animations that may still be referenced.
- Consider different screen resolutions and aspect ratios.
- Avoid changes that prevent users from accessing essential Minecraft menu functions.
- Prefer relative and portable resource references where supported.
- Do not assume a menu layout renders correctly without in-game verification.

---

## 10. Mod Management

The repository may intentionally exclude mod JAR files.

### Rules

- Do not download or add mods unless explicitly requested.
- Do not commit third-party mod JARs.
- Do not invent mod versions or download URLs.
- Verify mod loader and Minecraft version compatibility.
- Check required dependencies before suggesting additions or removals.
- Check whether other mods, quests, datapacks, or configurations reference a mod before removing it.
- Distinguish required dependencies from optional integrations.
- Consider client-only, server-only, and common-side requirements.

### Removing Mods

Before removing a mod, inspect relevant references in:

- Configurations
- FTB Quests
- Patchouli books
- Datapacks
- Resource packs
- Scripts
- Other mod dependencies

Report references that may become invalid.

A removed mod can affect existing worlds, including blocks, items, entities, and world generation. Do not assume removal is safe.

---

## 11. Performance & Stability

Prioritize stable gameplay, especially for multiplayer.

When evaluating performance changes:

- Distinguish client FPS from server TPS.
- Consider CPU, memory, disk, and network impact.
- Avoid treating memory usage alone as a performance metric.
- Do not recommend disabling required systems without checking dependencies.
- Prefer measurable changes over speculative optimizations.
- Avoid excessive logging or unnecessary periodic operations.

Do not claim a performance improvement without benchmarks or supporting evidence.

---

## 12. Distribution & Licensing

This modpack is distributed through CurseForge.

### Rules

- Respect third-party licenses and permissions.
- Do not assume that public downloads imply redistribution permission.
- Do not copy or redistribute restricted mod JARs.
- Do not assume giving credit replaces permission.
- Distinguish original project files from third-party content.
- Do not modify legal notices or credits without authorization.
- Do not assume the repository license applies to third-party assets.

If redistribution rights are unclear, flag the relevant files for review.

### CurseForge Releases

- Preserve valid CurseForge manifest information.
- Check files included in release overrides.
- Exclude unnecessary runtime files, logs, saves, and caches.
- Verify that required configurations and assets are included.
- Do not assume `.gitignore` controls CurseForge export contents.
- Do not publish or upload releases without explicit authorization.

---

## 13. Documentation

Documentation should be written primarily in English unless otherwise requested.

Keep documentation accurate, concise, and maintainable.

Important documents may include:

```text
README.md
CHANGELOG.md
docs/MODLIST.md
docs/CREDITS.md
docs/DEVELOPMENT.md
```

### Documentation Rules

- Do not invent completed features.
- Distinguish planned features from implemented features.
- Keep Minecraft and NeoForge versions accurate.
- Update relevant documentation when behavior changes.
- Keep credits and external links intact unless corrections are required.

---

## 14. Git Workflow

Use Conventional Commits.

Preferred formats:

```text
feat(scope): description
fix(scope): description
refactor(scope): description
perf(scope): description
docs(scope): description
chore(scope): description
```

Examples:

```text
feat(quests): add exploration quest chapter
fix(config): correct mob spawn configuration
fix(patchouli): resolve invalid item references
refactor(fancymenu): organize menu assets
perf(config): reduce unnecessary particle effects
docs: update modpack installation guide
chore(mods): remove incompatible mod references
```

### Git Safety

- Do not commit secrets or private account data.
- Do not force-push or rewrite history without authorization.
- Do not discard unrelated local changes.
- Do not automatically commit or push changes unless requested.
- Do not add generated Minecraft runtime files to Git.
- Keep commits focused on a clear purpose.

---

## 15. Validation & Testing

Use the smallest relevant validation steps for each change.

### Suggested Checks

**JSON**

- Validate JSON syntax.
- Check references and required fields.

**SNBT**

- Validate syntax using a compatible parser where available.
- Check IDs and dependencies.

**TOML**

- Validate syntax and setting types.
- Preserve comments when possible.

**Resource Packs**

- Verify paths and namespaces.
- Check referenced files exist.

**Datapacks**

- Validate expected structures.
- Check recipe, tag, and loot-table references.

**Mod Changes**

- Check dependency references.
- Review compatibility and side requirements.

### In-Game Testing

When applicable, recommend tests for:

- Client startup
- Dedicated server startup
- Joining multiplayer
- Existing-world loading
- New-world generation
- FTB Quests and rewards
- Patchouli books
- Custom menus
- Resource packs
- Gameplay compatibility

Never claim these tests passed unless they were actually executed.

---

## 16. Agent Response Format

For development tasks, provide a concise summary covering:

1. **Changes Made** — Files and behaviors modified
2. **Validation** — Checks actually performed
3. **Risks** — Compatibility, world migration, or licensing concerns
4. **Next Steps** — Only when additional action is necessary

Avoid lengthy explanations for trivial changes.

For planning or investigation tasks, distinguish verified findings from recommendations.

---

## 17. Final Principles

- Stability before new features.
- Preserve existing worlds whenever possible.
- Verify before changing.
- Do not invent Minecraft or mod-specific data.
- Keep changes small and traceable.
- Respect original creators.
- Prefer maintainability over complexity.
- Keep the modpack enjoyable.

# Working Conventions

- Agent collaboration and approval: Think independently to understand the task, identify risks, and prepare a recommendation, but present that recommendation and wait for explicit approval before making changes, executing a plan, or taking an external action. Do not decide and act beyond the user's explicit scope.
- If work cannot be completed safely or clearly—because requirements, authority, access, consequences, or a technical constraint are unclear—ask first. Do not force a workaround that changes scope or assumptions.

# Git Commit Message

Before making any change, present the proposed scope and wait for explicit user approval. This applies even to clear, small, low-risk, or cosmetic changes.
Ask before proceeding whenever scope is ambiguous, an action is destructive or irreversible, adds dependencies, changes external services, affects data outside the workspace, or cannot be completed as requested.
After completing code changes:
Summarize what changed.
List important files changed.
Mention any remaining concerns or follow-up work.
Suggest a concise Git commit message based on the actual changes.
Use Conventional Commits format when appropriate.
Never run git commit unless explicitly requested.
Never add AI/agent attribution to commits, tags, pull requests, or release notes (for example Co-Authored-By: Claude … or "Generated with …"). GitHub counts co-author trailers as repository contributors, and a pushed trailer cannot be removed without rewriting history.
Never run git push (branches, tags, or --force) or create a GitHub Release. Prepare the commit or tag locally, then hand the user the exact push/release command to run.
You are a senior software engineer reviewing git changes.

Your task:
Generate a high-quality commit message based ONLY on the relevant git changes.

Rules:

1. If staged changes exist (git diff --cached), use ONLY staged changes.
2. If no staged changes exist, use the regular git diff.
3. Never mix staged and unstaged changes.
4. Use Conventional Commit format.
5. Include scope if identifiable (e.g., auth, books, notes, editor, sync, search, ui, deploy, docs).
6. If Jira keys appear in the diff, include them after the scope.
7. Keep subject line concise (<= 100 chars).
8. Focus on business impact, not syntax noise.
9. Ignore whitespace-only or formatting-only changes.

Output format: feat(feature_name): short summary

Example:
fix(sync): keep local draft until Firestore write succeeds so typed text is never los

**Rest the weary heart.**
