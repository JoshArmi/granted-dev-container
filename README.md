# Granted Dev Container

This repository contains the latest iteration of my attempt to load the [granted](granted.dev) toolchain into a dev container.

## Goal

To provide a publicly available [feature](https://containers.dev/implementors/features/) for adding [granted](https://granted.dev) to dev containers.

## Executing against AWS

Authenticate against AWS by running commands such as `assume <your-role> --exec <your command here>`

## Current Issues

Please note that I believe both the following issues are user error, and not an issue with the tool itself.

### Environment Variables

To date, I have been unable to get the environment variables of the bash shell within the container to be populated correctly. Normally, by having the alias configured correctly, as in step 4, running assume will set the required environment variables for you to automatically authenticate as your chosen role.

While there are workarounds, I've found them hackier than using the --exec flag with assume for now.

### Passphrase Requirement

Currently being prompted for a password for ~/.granted/secure-storage-aws-sso-tokens during the authentication flow is less than ideal as we are in a transitory, single tenanted environment.
