# Conjur App Storage Workflows

This repository contains GitHub Actions workflows for self-service management
of Conjur variables in delegated `app_storage` environment sandboxes.

The current implementation is intended for LAB and pilot use.

## Available workflows

### Create Or Update Conjur Secret

The workflow:

1. derives the Conjur workload identity from the entered SAS and environment,
2. authenticates the corresponding workload to Conjur,
3. calculates the target `app_storage` environment branch,
4. creates the Conjur variable,
5. assigns the default environment management group,
6. writes the supplied secret value to the variable.

### Share Conjur Secret

The workflow adds a `read` and `execute` permit for a selected Conjur group
to an existing variable.

## Repository structure

```text
.github/
├── actions/
│   └── conjur-authn/
│       └── action.yml
└── workflows/
    ├── create-or-update-secret.yml
    └── share-secret.yml

README.md
