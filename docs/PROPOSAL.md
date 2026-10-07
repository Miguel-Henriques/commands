# Commands - Never have to keep documentation any more for your project commands

## Motivation

After years of experience working across different companies and teams with unique setups, there was a particular moment that I always felt was unnecessarily inneficient: running commands. And by that I don't in fact mean the step of running a command, but all of the other steps it takes in between to discover or remember what that command or sequence of comands is.

Working on software projects requires you to do any of the following at some point:
    build, deploy, run custom scripts, run tests, load credentials and/or authenticating against third-party providers, run locally..

And you could argue you remember every one of these commands for your project(s). And that's fine. I used to do as well. But remembering all commands by heart stops being reasonable when you work across multiple different repositories, managed by different teams/customers, with different ways of working, on different tech stacks. That's why teams create supporting documentation. However, without standardization, the documentation does not solve the problem, it just shifts it: from "What's the command" to "What's the document that contains the commands".

Efficient Context Switching therefore requires a standardized process that serves project-specific commands under a unified interface.

## Intro

Commands is a terminal-based application from where you can list and run project-scoped commands.

It is designed for collaborative work, with command definitions committed to version control under a `commands.yaml` file that lives at the root of your project.

## Usage

1. Install

Commands can be installed with most popular package managers: Homebrew, npm, (windows solution)
```sh
brew install commands
npm install -D commands
```

2. `commands.yaml`

These definitions should be placed at a `commands.yaml` file at the root of your project.

```yaml
Version: 1.0

Commands:

  terraform_init_backend:
    Name: Terraform init - Backend
    Description: Initialize the Terraform backend for the current environment
    Command: terraform chdir init -backend-config="./environments/$TARGET_ENV/config.tfbackend"
```

3. Run

```sh
commands

# // WIP
```

See [spec](#spec) for the full commands file spec. 

## Spec

See [spec.yaml](../specs/v1.0/spec.yaml) for the latest official Commands specification.

## FAQ

### How does it compare to zsh aliases ?

With aliases you still have to remember the command alias or be inspecting the `.zsh` file everytime you need to look it up.
Commands is designed for collaborative work, and targeted on a per-project basis. Commands are not global.