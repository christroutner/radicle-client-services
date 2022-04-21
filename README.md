# Radicle Client Services

This is a fork of [radicle-client-services](https://github.com/radicle-dev/radicle-client-services). It has been customized to create a Radicle Seed Node for my own personal use and members of the Permissionless Software Foundation. The purpose of this seed node is to mirror our code and create a redundant backup, in case GitHub ever tries to censor our code.

## Changes
The Seed Node is operated via Docker Compose. The original Docker Compose file had the following changes applied to it:

- The `--allow-unauthorized-keys` is applied to the git-server to allow any radicle key to push to it.
- The `caddy` Docker file is disabled. The functionality it provides is replaced by nginx.
