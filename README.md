# Identities
Public keys of people assosciated with apinf

## Why?
Sharing passwords is bad. When creating new machines or granting people access, initial passwords tend to be predictable, or complex and difficult to share, which usually end up in emails/messages. Users tend to repeat passwords between services.

Passwords in general are bad. Not everyone uses a password manager.

SSH passwords are a crime. Let's do identity based access only.

## How?

Everyone who is expected to have ssh access to apinf's dev and testing machines should create a file under `ssh` with their github username, ending in `.keys`. @phanimahesh, for instance, will have `phanimahesh.keys`. The file is in `authorized_keys` format - one public ssh key on each line.

We'll use this as a database-of-identities. When someone needs access to some server, we simply add their keys to the appropriate user account's `authorized_keys`.

## Why a separate repo? Why not `https://github.com/<username>.keys`?

Explicit is better than implicit. It's easier to keep track of changes to the repo, plus we can do fancy automation with this.

## Why is this public?

This repo is intended to hold only public keys, which, by definition, are expected to be public. There is risk of information leakage here, we are aware, but prefer this for convenience since the only information leaked is the active members with access to servers and their list of keys. We may go private at some point.
