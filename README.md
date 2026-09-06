# Rhea Homebrew Tap

**A doorway must say where it leads.**

This tap installs the `rhea` command-line client. One formula identifies the source release, Python runtime, and dependency resources that Homebrew assembles into an isolated Python environment.

An installation command is a chain of trust disguised as a short sentence. Make the chain readable: where the code comes from, which version you get, and what appears in your terminal.

## Install the command

With Homebrew available:

```bash
brew tap timelabs-npo/tap
brew install timelabs-npo/tap/rhea
rhea --help
```

The formula is named **`rhea`**. The underlying Python distribution is **`rhea-cli`**. Installation supplies the client; backend services and your GitHub/Fly.io authorization are separate prerequisites for the operations that use them.

## Follow the package

```text
Formula/rhea.rb
  ├── rhea-cli v0.1.0 source archive + checksum
  ├── Python 3.11 + pinned dependency resources
  └── Python virtual environment → rhea command
```

[Formula/rhea.rb](Formula/rhea.rb) currently points to the `rhea-cli` **v0.1.0** GitHub tag. Installing this formula therefore does not imply that you have the newest commit on the CLI's main branch.

The formula uses `virtualenv_install_with_resources`. Its declared test checks the output of `rhea --help`; that checks a small CLI entrance, not backend health, a successful deployment, or agent coordination.

## Choose what to do next

Start with `rhea --help` and `rhea api --help`, then read [the CLI's command guide](https://github.com/timelabs-npo/rhea-cli). Repository operations need `gh`; Fly.io operations need `fly`; both need the relevant authentication. Service requests need a compatible reachable backend.

This tap owns the installation recipe. Its dependency pins may differ from the formula copy inside the CLI repository, so use [this formula](Formula/rhea.rb) when inspecting what this tap installs.

The ambition is a small, inspectable entrance into a larger system. Even a doorway deserves a visible destination.

## The surrounding system

- [Rhea family entrance](https://blueshoes.space/rhea/) — find the components and their roles.
- [Rhea CLI](https://github.com/timelabs-npo/rhea-cli) — source and behavior of the installed command.
- [Rhea / Tribunal](https://github.com/timelabs-npo/rhea-project) — coordination and service work addressed by the client.
