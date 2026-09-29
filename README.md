# Signal Translator

Three skills that walk you through preparing one application: index the signals in a job description, map your background against them to show matches and gaps, find the career arcs your evidence supports, then scaffold your CV.

Human-first: you give your own read of the role before the tool adds anything, and the tool is designed not to write your application prose. It indexes, maps, and structures. You write every word that goes into a real document.

Why: the aim is to help you build the skill of spotting your own strengths, and to own what you find. It also keeps your application within the rules when an organisation asks for no AI drafting.

## Status

0.2.0 (updated 28 September 2026), an ongoing experiment. Known issues and next steps are tracked in a backlog; ask about them in Discussions.

## Install

1. Download the plugin `.zip` file from this repository. Don't unzip it.
2. In Claude, open **Settings → Plugins** and choose **Add**.
3. Upload the file you downloaded.

*Menu names and path as of September 2026; they may change.*

## Use

Start a conversation and say something like "help me prepare an application for this role". The `use-this-signal-translator` skill is the entry point: it runs all three parts back to back and hands off between them on your confirmation.

| Skill | Role | Produces |
| --- | --- | --- |
| `use-this-signal-translator` | Entry point, runs the sequence | nothing itself |
| `signal-index` | Part one | `signal-index.md` |
| `match-map` | Part two | `match-map.md` |
| `cv-scaffold` | Part three | `cv-scaffold.md` |

The three parts also run on their own if you invoke one by name, for example when you only want to index a job description.

You can run all three parts in one conversation. In a folder-based setup (such as Claude Code, or the desktop app working in a folder), you can also stop and resume later: create a folder for each application and start the conversation in it. The tool saves each part under a fixed file name, so when you come back it finds what it has already written and picks up from there.

## Editing

Each skill lives in `skills/<name>/SKILL.md`. The file name must stay `SKILL.md`; the folder name identifies the skill.

Every `SKILL.md` has two parts: the instructions for that part, and an **Operating contract** section at the end, holding the rules shared by all four skills. The four copies of the Operating contract are identical. If you change it in one file, make the same change in the other three, so they stay identical.

## History

Started as a prompt guide for AI safety applicants, then a standalone web app. 0.1.0 was the first plugin version.
