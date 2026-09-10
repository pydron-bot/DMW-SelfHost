# Claude Personal Assistant

A private, self-hosted personal assistant for a **single user** — the project owner.
It connects to the owner's own Google account to help manage email and calendar:
reading and summarizing messages, drafting and sending replies the owner asks for,
and viewing or creating calendar events on request.

- **Users:** one — the project owner. Not offered to the public, no sign-ups.
- **Hosting:** runs on the owner's private server; nothing is exposed to the internet.
- **Not affiliated with Google or Anthropic.** "Claude" refers to the Anthropic
  language model the assistant is built on.

## What Google data it accesses

| Scope area | Why |
|---|---|
| Gmail — read, compose, send, labels, basic settings | summarize the inbox, draft and send mail the owner requests, organize with labels |
| Google Calendar — read and write | answer schedule questions, create and update events on request |

The assistant only ever acts on the account of the person who authorized it.

## Policies

- [Privacy Policy](PRIVACY.md)
- [Terms of Service](TERMS.md)

## Contact

pydron@gmail.com
