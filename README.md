# Radicle Client Services

This is a fork of [radicle-client-services](https://github.com/radicle-dev/radicle-client-services). It has been customized to create a Radicle Seed Node for my own personal use, for members of the [Permissionless Software Foundation](https://psfoundation.cash), and for [Cash Stack](https://cashstack.info) devs. The purpose of this seed node is to mirror our code and create a redundant backup, in case GitHub ever tries to censor our code.

## Changes
The Seed Node is operated via Docker Compose. The original Docker Compose file had the following changes applied to it:

- The `--allow-unauthorized-keys` is applied to the git-server to allow any radicle key to push to it.
- The `caddy` Docker file is disabled. The functionality it provided is replaced by nginx.
- The volumes mounted by the containers are moved to a detachable hard drive.

## Networking

The following ports are exposed:

- 8778 - points to the git server
- 8777 - points to the http server

Using nginx, radicle.fullstackcash.nl proxies to the git server on port 8778. I'm still trying to figure out how to connect the http server. But issuing `rad push --seed radicle.fullstackcash.nl` command with [radicle-cli](https://github.com/radicle-dev/radicle-cli) will push the code to the seed node.

The main objective of this repository and the seed node server is to provide a redundant location, under the control of the PSF, to upload code besides GitHub and the community Seed nodes that Radicle provides.
