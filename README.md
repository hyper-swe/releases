# HyperSWE

HyperSWE is built for reviewing code that coding agents write. A
line-by-line review of an agent's change is slow and impractical, and it
can still leave you unsure what the change does when you approve the
merge.

HyperSWE records each change in a receipt trail: the acceptance stories
you set, the tests that ran, an independent review and every gate
decision. You or your agent can run `hyperswe loop verify` to check the
trail's internal consistency. Read the report on the review page of the
HyperSWE app. Open the findings, available codemap impact and receipts
when you need detail. At each of the two approval gates, you approve,
decline or steer the agent with an instruction.

The HyperSWE app and CLI also provide:

- Overview tab: a first look at the codebase in numbers, each naming its
  source.
- Map and Features tabs: the codemap, with a lens that highlights a
  feature, a command or a config key.
- Debt tab: code smells and technical debt, computed deterministically.
- Production errors: `hyperswe trace` places the resolved frames of a
  traceback on the codemap.
- Audited worktrees: each change runs in a separate audited worktree with
  its history kept by `mgit`.
- Delete guard: `hyperswe init` installs a guard that refuses agent
  commands that delete a directory tree in one step.

## Before you begin

You need:

- macOS on Apple silicon or Linux on x86-64.
- `curl` and Git.
- A coding agent that reads `CLAUDE.md` or `AGENTS.md`.
- A reviewer that did not write the change: another session, model or
  person. In mode 2, you obtain the review; HyperSWE does not call the
  reviewer for you.

Choose one small change with a test you can run. The command examples below
were checked with v0.2.0-beta-rc3.

## Install the suite

1. Run the installer:

   ```sh
   curl -fsSL https://github.com/hyper-swe/releases/releases/latest/download/install.sh | sh
   ```

   It installs `hyperswe`, `mtix`, `mgit` and sandbox support files in
   `$HOME/.local/bin` by default. It does not initialize repositories.
   Add that directory to your shell profile's `PATH` if needed.

2. Check the installed build:

   ```sh
   hyperswe version
   ```

The installer compares downloads with `checksums.txt` and separately
reports whether it checked the signature. To select a release, set
`HYPERSWE_RELEASE_TAG` for the installer process.

## Set up a repository

1. Run the installation check:

   ```sh
   hyperswe doctor
   ```

   Read the results before continuing. A `?` result means not checked, not passed.

2. Run `init` from the root of each repository you want to use:

   ```sh
   cd /path/to/your/repo
   hyperswe init
   ```

   Re-run it after an upgrade to update the instructions and managed hooks.

3. Build the repository map:

   ```sh
   hyperswe index -repo .
   ```

For setup without the delete guard or automatic inbox wake hooks, use:

```sh
hyperswe init -no-rm-guard -no-wake
```

Without a terminal, `init` installs the project delete guard by default
unless you pass `-no-rm-guard`. These flags skip installing those settings;
they do not remove settings already installed.

## Review your first change

1. Open your coding agent in the repository. Ask it to fix the small
   problem you selected and use the HyperSWE loop in mode 2. Specify that it
   must agree on the acceptance stories and test command with you, obtain
   an independent review, show both gate blocks unchanged, and stop for
   your decision at each gate.

2. At gate 1, inspect the plan and test command. Approve, decline or steer
   the plan. Setup and baseline checks can run before this gate; approval
   permits work on the change.

3. Have your agent obtain a review from the reviewer you selected. Give
   the reviewer the change, acceptance stories and test evidence. Submit
   the review as written, before fixing its findings:

   ```sh
   hyperswe loop submit <run-id> -review @review.txt -reviewer "<reviewer-name>"
   ```

   `review.txt` uses the `FINDINGS`, `STORY CHECK` and `SUMMARY` sections
   specified in `HYPERSWE.md`. Use `-reviewer` on every submission. A review
   without a declared reviewer is not recorded as independent. HyperSWE
   checks the declared reviewer against the author, not model identities.

4. At gate 2, inspect the test results, review findings and proposed merge.
   Approve, decline or steer the work.

5. Start the local review app:

   ```sh
   hyperswe app -repo .
   ```

   Open http://127.0.0.1:7440/#reviews and select your run. The page shows
   findings and available codemap impact: mapped code paths the change
   could affect. Missing impact is shown as not recorded. The app uses the
   map built by `index` and runs on your machine. Use `hyperswe app -h` to
   check the address flag if you need another port.

6. Check the recorded trail:

   ```sh
   hyperswe loop verify <run-id>
   ```

   It recomputes the receipt chain and, with repository context, checks
   recorded approvals and the merge. This checks internal consistency;
   it does not prove that the entire record could not be rewritten.

For Python projects, run tests with `PYTHONDONTWRITEBYTECODE=1` to avoid
adding `__pycache__/` files to the change. Before gate 2, ask your agent to
check for generated files and remove only files it created for the tests.
Do not delete existing repository files or run a recursive directory delete.

### Configure reviewer access

Mode 2 uses your agents' own credentials. It needs no model key in
HyperSWE. If the reviewer uses an API, put its key in that reviewer's
process environment, not in a prompt, review file or Git commit. For
HyperSWE-managed API bindings, `api_key_env` stores the
environment variable name, never the key. `hyperswe config models` shows
the bindings. The separate `hyperswe loop run` mode needs developer and reviewer engines
configured.

### Delegate gate decisions

By default, ask your agent to stop at both gates. For auto mode, explicitly
instruct your agent to decide the gates within the scope, acceptance
criteria and test command you provide. Require independent review, tests
and reviews in the loop record, and a stop for decisions outside that
scope. Auto mode is a mode 2 instruction to your agent, not a switch for
`hyperswe loop run`.

## Inspect repository changes

`hyperswe init` writes `HYPERSWE.md`, adds a pointer to it in `CLAUDE.md`
and `AGENTS.md`, and sets up repository-local agent settings. The loop uses
`mgit` for audited change history. Setup includes a project delete guard
unless you disable its installation.

For production errors, use `hyperswe trace` to place resolved traceback
frames on the codemap. It reports frames it cannot resolve. This does not
establish the root cause of an error. Use `hyperswe trace -h` for input
options.

## Remove repository settings

1. Remove the instructions and managed settings:

   ```sh
   hyperswe detach
   ```

   It removes the managed pointer lines, generated `HYPERSWE.md` when it
   has no other content, and the settings added by `init`. It preserves
   unrelated instructions and settings.

2. Inspect the retained local state:

   - `.hyperswe/`: receipts, sessions, worktrees and the repository map.
   - `.mgit/`: audited change history.
   - `.mtix/`: the local work tracker.

3. Before removing retained state, finish or cancel runs, save work, and
   archive the receipts and sessions you need. Keep receipts if you need
   the trail checked by `hyperswe loop verify`. Inspect the files, then
   use the removal commands that `hyperswe detach` prints for directories
   you no longer need. These commands delete the retained local state.

Detach does not uninstall the suite commands.

## Check beta status

HyperSWE is in beta.

The [HyperSWE Beta Terms of Use](https://github.com/hyper-swe/releases/blob/main/TERMS.md) govern your use of the beta.

## Find release information and help

This repository carries release archives, signed checksums and the
installer, not the HyperSWE core source. Each tag's release notes list its
changes. Use `hyperswe version` to identify your installed build.

Use `hyperswe help` to list commands and `hyperswe loop <verb> -h` to check
a loop verb's flags. `hyperswe init -h` covers repository setup,
`hyperswe mcp -h` covers MCP clients, and `hyperswe feedback -h` covers
feedback settings.
