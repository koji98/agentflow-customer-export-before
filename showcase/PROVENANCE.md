# Where this example came from

[Back to the app guide](../README.md)

This is the broken app used at the start of the recorded run. It includes the task to fix the download and add a preview.

The original app came from Git commit `e875f94c455716bcd33162b5f95a4224897d33ec`. Its code, page, customer data, and app tests are unchanged here.

The `before-agentflow` tag saves the first public copy at commit `e72e8a5124b408505040a60913b54137d98f14d2`. A tag is a name for a saved point in Git history.

## Which versions were used?

| Part | First saved run | Current setup guide |
| --- | --- | --- |
| Node.js | 24.18.0 | 24.18.0 |
| Python | 3.12 | 3.10 or later |
| Codex CLI | 0.142.2 | 0.144.5, tested during setup checks |
| Model | GPT-5.5, medium reasoning | The graph lets Codex choose its default |
| Agentflow | `bf7399955a45ea9e8fe0959c64be7a06649d997f` | `460fdf31d94390a1aaf12a8f309ebcbf8c4b1d13` |

First run Agentflow commit: `bf7399955a45ea9e8fe0959c64be7a06649d997f` in [koji98/agentflow](https://github.com/koji98/agentflow).

The graph says `"model": "auto"`. A later run may use a different model and get a different result. See [Run the workflow](RUN.md) for setup steps.

## What changed when we shared the example?

We changed file paths so the graph can run from a new clone. The check command now uses tools inside `showcase/acceptance/`. The app notes are in `APP_GUIDE.md`.

We also told the AI to leave the workflow and showcase files alone. The task, AI scoring rules, score limits, and number of tries stayed the same.

In the original run, the check tools lived outside the app folder. Here, they live in the repo and have their own copy of the expected data. The rules tell the AI to leave them alone.

## What was added later?

We added setup guides, `.nvmrc`, a lockfile, the doctor tool, and GitHub checks for Linux and macOS. We then rewrote the reader guides in plain English.

These changes did not change the app code or the original task files. The saved Git tags still point to the same before and after copies.

## September 24 rerun

The rerun started from this repo at `8c5387e80a736ceeda41994c1af93b41881b8340`. It used the merged network permission fix, Codex CLI 0.144.5, and GPT-5.6-sol in its direct worker and judge logs. The graph stayed unchanged. The current guides were updated after that run. Read the [new results and source notes](https://github.com/koji98/agentflow-customer-export-after/blob/main/results/2026-09-24/PROVENANCE.md).
