# MickyVX Technical Learning Journal

A chronological, evidence-based engineering and learning journal documenting the development of **MickyVX Phantom 1.0** — a customized cybersecurity Linux distribution derived from Parrot Security.

This repository is the main Git home for the journal. It records what was actually done, how it was done, why technical decisions were made, what was learned, what failed, and what remains to be verified.

> **Journal principle:** Record the engineering reality, not the idealized version. Planned work is not completed work, a command succeeding is not always a functional test passing, and an unresolved problem must remain marked unresolved.

---

## Purpose

The journal is intended to serve as:

- **Development history:** a chronological record of MickyVX engineering sessions.
- **Learning resource:** explanations of Linux, Debian, Parrot, networking, security tools, shell scripting, Git, and distribution engineering concepts encountered during development.
- **Troubleshooting record:** symptoms, diagnostic evidence, hypotheses, root causes, corrective actions, and verification results.
- **Decision log:** technical choices, their rationale, trade-offs, and whether they are final or provisional.
- **Project-state record:** what is implemented, tested, incomplete, blocked, or still unknown.

The journal complements the MickyVX source/build repository. It documents the work and learning process; it is not itself proof that the distribution can be rebuilt or that a feature works.

## Repository structure

The journal uses one Markdown file per development day.

```text
MickyVX-Technical-Learning-Journal/
├── README.md
├── day-01-xfce-git-baseline-audio-investigation.md
└── day-XX-short-session-topic.md
```

As the journal grows, supporting folders may be added when there is a real need, for example:

```text
├── notes/
├── diagrams/
└── references/
```

Do not add folders or placeholder entries merely to make the repository look complete. Keep daily entries easy to find and link.

## Journal entries

| Entry | Date | Focus | Status |
|---|---|---|---|
| [Day 1 — XFCE, Git baseline, and audio investigation](day-01-xfce-git-baseline-audio-investigation.md) | 2026-10-15 | XFCE setup, initial Git commit, VMware guest audio investigation | XFCE reported working; audio unresolved |

New entries will be added as development sessions are documented. The table should reflect actual entries and verified status only.

## Entry format

Daily entries generally follow this structure:

1. Daily Overview
2. Goals for the Day
3. Technical Work Performed
4. Commands and Their Explanations
5. Files, Configurations, and Code Changes
6. Problems, Errors, and Root-Cause Analysis
7. Git and Source-Control Activity
8. Technical Concepts Learned
9. Verification and Test Results
10. Decisions and Their Rationale
11. Current Project State
12. Lessons Learned
13. Remaining Tasks
14. Next Session Plan
15. Daily Summary

Sections may be adapted when genuinely irrelevant, but important evidence and project-state information should not be omitted.

## Evidence and accuracy policy

Accuracy takes priority over completeness or presentation.

- Record only commands, outputs, changes, commits, and tests supported by the session notes or other evidence.
- Clearly distinguish **completed**, **attempted**, **failed**, **proposed**, **planned**, and **unverified** work.
- Do not describe a recommendation as an action that was performed.
- Do not call a feature functional merely because a command ran without an error.
- Do not invent root causes. Label uncertain explanations as hypotheses.
- Preserve meaningful error messages and relevant output.
- If verification was not performed, say so.
- If two source records conflict, document the inconsistency rather than silently choosing one.
- Never include passwords, private keys, access tokens, recovery codes, or other secrets.
- Avoid copying sensitive personal data, machine identifiers, or private infrastructure details unless they are necessary and safe to retain.

### Status vocabulary

| Status | Meaning |
|---|---|
| **Completed** | The described task was performed and the stated outcome is supported by evidence. |
| **Reported working** | The source notes report success, but the journal does not have independent verification evidence. |
| **Attempted** | The action was tried; success is not established. |
| **Failed** | The action produced a failure or did not achieve its intended result. |
| **Unresolved** | The problem remains open; no verified fix is recorded. |
| **Planned** | Intended future work; not yet performed. |
| **Unverified** | A change or result may exist, but the necessary check has not been recorded. |
| **Blocked** | Progress depends on missing information, access, or another prerequisite. |

## Naming convention

Use lowercase filenames with hyphens:

```text
day-01-xfce-git-baseline-audio-investigation.md
day-02-project-structure-and-documentation.md
day-03-desktop-customization.md
```

The examples after Day 1 are naming examples only. Use a day number, date, and topic only when they are established by the source material. Do not invent chronology.

## Adding a new journal entry

1. Gather the engineering handoff, session summary, terminal output, relevant diffs, and test results.
2. Confirm the date and day number. If either is unknown, mark it as provisional rather than guessing.
3. Create a new Markdown file using the naming convention.
4. Write the entry in chronological order and explain the important technical mechanisms.
5. Separate actual work from proposed next steps.
6. Update the **Journal entries** table in this README.
7. Preview the Markdown and check links, code fences, and filenames.
8. Review the Git diff for accidental secrets or unsupported claims.
9. Commit the entry and README update together when both are ready.

Example Git workflow:

```bash
# Move to the local journal repository.
cd /path/to/MickyVX-Technical-Learning-Journal

# Check the current branch and working-tree state.
git status --short --branch

# Review which files are present and changed.
git diff --stat
git diff -- README.md

# Stage only the journal entry and README update.
git add README.md day-XX-short-session-topic.md

# Review exactly what is staged before committing.
git diff --cached

# Commit the documentation update.
git commit -m "docs: add Day XX development journal"
```

Replace the example path and filename with the actual repository path and entry name. These are workflow examples, not commands claimed to have been run.

## Git practices

- Keep the journal in its own Git repository if that is how the project is organized.
- Use clear, descriptive commit messages.
- Prefer small commits that represent a coherent journal update.
- Review `git diff` before staging and `git diff --cached` before committing.
- Do not use `git reset --hard`, force-push, or destructive cleanup commands as routine journal maintenance.
- Do not commit secrets, private keys, passwords, tokens, or sensitive host/VM data.
- Do not rewrite historical entries merely to make past work appear more successful. If later evidence changes the understanding, add a dated correction or clearly documented update while preserving the original record.
- A Git commit preserves journal files; it does not automatically back up the repository. Use an appropriate remote or backup process if you need off-device protection.

## Technical scope

The journal may document topics encountered during MickyVX development, including:

- Linux filesystem layout, users, groups, permissions, processes, and services.
- Debian packages, dependencies, APT repositories, package signing, and upgrades.
- Parrot Security customization and distribution maintenance.
- XFCE, display outputs, desktop configuration, and window managers.
- Networking, protocols, and security tooling.
- Shell scripting, automation, and error handling.
- Git history, branches, diffs, tags, and releases.
- Live systems, persistence, bootloaders, ISO construction, and validation.
- Troubleshooting methodology, testing, recovery, and risk management.

Explanations should be relevant to the work recorded in each entry, not added as unrelated reference material.

## Relationship to the MickyVX build repository

This repository is the **technical learning journal**, not the MickyVX operating-system source repository.

- The build/source repository should contain the implementation: scripts, configuration, packaging, build definitions, and other maintained project assets.
- This journal repository should contain the chronological engineering record and learning explanations.
- When useful, journal entries may refer to source files, commits, branches, or release identifiers from the build repository.
- Do not assume that a configuration is reproducible just because it is described in the journal. Reproducibility requires maintained source artifacts and successful verification.

## Contributing to the record

This is a personal project journal. Updates should preserve the evidence-first rules above. If another person contributes notes or corrections, identify the source and distinguish their observations from work personally performed during a development session.

## License and sharing

No license is specified by this README. Add a license only after deciding how the journal may be reused and shared. Before publishing, review entries for private paths, host details, usernames, device identifiers, network information, and accidental secrets.

---

**Project:** MickyVX Phantom 1.0  
**Repository:** MickyVX Technical Learning Journal  
**Format:** Markdown  
**Primary rule:** Evidence first. Document what happened, explain why it matters, and leave unknowns clearly marked.
