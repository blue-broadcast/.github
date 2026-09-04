# Contributing to BlueBroadcast

Thanks for your interest. This guide applies to **all repos** in the
organization unless a specific repo says otherwise.

## Where to post what

| Topic | Where |
|---|---|
| Idea, design proposal, **RFC** (new profile, protocol extension) | **Issue** on the relevant repo, `enhancement` label |
| Usage question | **Issue** on the relevant repo, `question` label |
| Reproducible bug | **Issue** on the relevant repo, *Bug* template |
| Fix or feature | **Pull Request** on the relevant repo |
| Security vulnerability | **NO public issue** - see [`SECURITY.md`](SECURITY.md) |

## Licenses - know this before contributing

| Repo | License | What it means |
|---|---|---|
| `omt-android` - **SDK** (`omt-sdk/`) | **Proprietary** (EULA) | no external SDK code contributions; issues and feedback welcome |
| `omt-android` - `sample-app/`, tooling | MIT | PRs welcome |
| `omtplugin` | GPL-2.0 | any contribution is licensed under GPL-2.0 |
| `libomtnet` (fork) | MIT | any contribution is licensed under MIT |
| `omt-h264` (proposal) | CC-BY | spec proposal + demo, aimed at upstream OMT |

By opening a PR, you confirm you have the right to submit the code under the
repo's license.

## Pull Requests

1. **One PR = one topic.** Describe the *what* and the *why*, not just the *how*.
2. Follow the repo's style. For `omt-android`: comments and logs are
   **in French** (a project convention), `./gradlew` must stay green
   (including `:omt-sdk:apiCheck` for any public Kotlin change).
3. Add or adapt tests when behavior changes.
4. Link the originating issue.

## Commit style

Conventional Commits (`feat:`, `fix:`, `build:`, `docs:`, `refactor:`...),
short messages, in the repo's language.

## The H.264 proposal (`omt-h264`)

This is a **standards proposal**. The end goal is an upstream submission to
[openmediatransport](https://github.com/openmediatransport). Feedback on the
FourCC, the frame format, and **capability negotiation** is the most useful
- open an `enhancement` issue on `omt-h264`.
