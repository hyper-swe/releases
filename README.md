# HyperSWE releases

HyperSWE reads a repository and answers three questions: what is in it,
where the risky parts are, and where a production error actually
happened. It also runs a gated review loop with your own coding agent,
if you bind one. This repository carries only the release archives,
their signed `checksums.txt`, and the installer; the source is not here.

Install the suite (`hyperswe`, the `mtix` coordinator, `mgit`
audited-git) with:

```sh
curl -fsSL https://github.com/hyper-swe/releases/releases/latest/download/install.sh | sh
```

The installer checks every download against `checksums.txt` before it
unpacks anything and says so when it cannot. To install a specific
release, set `HYPERSWE_RELEASE_TAG=<tag>` first. `hyperswe version`
reports which build you have.

## Quick start

You need macOS on Apple silicon or Linux on x86-64, `curl`, a git
repository, and a coding agent that reads `CLAUDE.md` or `AGENTS.md`.
This quick start needs v0.2.0-beta or newer: earlier releases don't have
`hyperswe detach`, `hyperswe init -files` or the delete guard.
`hyperswe version` shows which build you have.

1. Install the suite with the command above.
2. From the root of your repository, run `hyperswe init`. It writes
   `HYPERSWE.md` (the instructions your agent reads) and one pointer line
   to it in `CLAUDE.md` and in `AGENTS.md`, and it asks whether to install
   a guard that blocks an agent's recursive deletes.
3. Open your coding agent in the repository and ask for a change you want
   reviewed. The agent starts a run, makes the change in an isolated
   worktree, and shows you two gates: you approve, decline or steer at
   each one.

To undo step 2, run `hyperswe detach`. It removes `HYPERSWE.md`, the
pointer lines and the settings `init` added, and leaves the rest of each
file as it was. The release notes for each tag list what changed.

## More help

The binary carries its own help. `hyperswe help` lists every command.
`hyperswe init -h` covers setting up a repository, and `hyperswe loop`
lists the review loop's verbs; add `-h` to a verb for its flags.
`hyperswe mcp -h` says how to connect an MCP client, and
`hyperswe feedback -h` covers sending feedback and turning it off.
