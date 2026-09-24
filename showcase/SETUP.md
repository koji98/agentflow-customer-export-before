# Help with setup

[Back to the app guide](../README.md) · [Run Agentflow](RUN.md)

Start with `npm run doctor` in the app's folder. It checks Node.js, Git, Python, and whether your computer lets the app start a local server.

## Use the right Node.js version

This app uses **Node.js 24.18.0**. The `.nvmrc` file tells nvm which version to use.

```sh
nvm install
nvm use
node --version
```

The last line should print `v24.18.0`. Run `nvm use` again each time you open a new terminal in this repo.

If the terminal says `nvm: command not found`, [install nvm](https://github.com/nvm-sh/nvm#installing-and-updating). Then close and reopen the terminal.

## Check Python and Git

```sh
python3 --version
git --version
```

Python must be **3.10 or later**. The checks call it by the name `python3`.

If a tool is missing, install it from [Python downloads](https://www.python.org/downloads/) or [Git downloads](https://git-scm.com/downloads). Then reopen your terminal.

## Common errors

| What you see | What to do |
| --- | --- |
| `EBADENGINE` or the wrong Node version | Run `nvm use` in this terminal. Then try the command again. |
| `python3: command not found` | Install Python 3.10 or later. Reopen the terminal and check `python3 --version`. |
| `EADDRINUSE` | Another app is using the same port. Stop it, or run `PORT=4321 npm start`. Open the new URL printed by the app. |
| `EPERM` or `EACCES` when a server starts | Your terminal or runner blocks local servers. Try a terminal on your own computer that allows them. |
| `Missing script` or no `package.json` | Use `cd` to enter the app's folder. Run the command there. |

The app needs no extra npm or Python packages. You do not need Docker, a database, or a secrets file. `npm ci` checks the saved package setup. `.npmrc` stops the install if you use an unsupported Node version.

## Failed checks in the before app

The before app has bugs on purpose. This is the expected result:

- `npm test`: all 6 tests pass.
- `npm run check:acceptance`: 16 of 29 checks pass, then the command ends with an error.
- Five of those failed checks show HTTP 404 because the preview does not exist yet.

The current after app should pass all 13 app tests and all 29 export and preview checks.

## Check the setup tool itself

```sh
npm run test:setup
```

All four tests should pass. They cover missing tools, old Python, and a signed-out Codex account. They also check that the setup tool does not print account details.

GitHub Actions runs the checks on Linux and macOS when we push changes. It does not need an AI account.

For Codex login or Agentflow install problems, see [Run the workflow](RUN.md#help-with-the-ai-tools).
