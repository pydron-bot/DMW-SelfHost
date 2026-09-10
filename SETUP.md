# Publishing this for the Google OAuth consent screen

Google's Branding page wants a homepage, a privacy-policy URL, and a terms URL on
an authorized domain before it will let you publish the app out of "Testing".
These three files cover it.

## 1. Put the files on GitHub Pages

1. Create a **public** repo, e.g. `pydron-bot/claude-pa`.
2. Add `README.md`, `PRIVACY.md`, `TERMS.md` from this folder.
3. Repo **Settings → Pages** → Source: *Deploy from a branch* → `main` / `/ (root)` → Save.
4. Wait ~1 min. Site is at `https://pydron-bot.github.io/claude-pa/`.
   - Homepage: `https://pydron-bot.github.io/claude-pa/`
   - Privacy:  `https://pydron-bot.github.io/claude-pa/PRIVACY`
   - Terms:    `https://pydron-bot.github.io/claude-pa/TERMS`
   (GitHub's Jekyll renders each `.md` to a page and lets you drop the `.html`.)

## 2. Fill in the Google Cloud "Branding" page

| Field | Value |
|---|---|
| App name | Claude Personal Assistant |
| User support email | pydron@gmail.com |
| App logo | *leave blank* — uploading one forces verification |
| Application home page | `https://pydron-bot.github.io/claude-pa/` |
| Application privacy policy link | `https://pydron-bot.github.io/claude-pa/PRIVACY` |
| Application terms of service link | `https://pydron-bot.github.io/claude-pa/TERMS` |
| Authorized domains | `github.io` |
| Developer contact email | pydron@gmail.com |

Save.

## 3. Publish

**Audience** page → **Publish app** → confirm. Status becomes "In production".
You'll still see an "unverified app" warning at consent time (Advanced → continue) —
that's fine and expected. The win: refresh tokens no longer expire after 7 days, so
`reauth.sh` becomes a rare thing instead of weekly.

## If Google rejects `github.io` as an authorized domain

Try removing the Authorized domains entry entirely and save — the loopback redirect
(`http://localhost`) doesn't require an authorized domain, and the policy links may
go through without one. If it still insists, point the three links at the raw repo
instead (`https://github.com/pydron-bot/claude-pa/blob/main/PRIVACY.md`, etc.) and
add `github.com` as the authorized domain.

## After publishing

Google may email about verification for the restricted Gmail scopes. For personal
use at 1 user you can ignore it; the app keeps working. If it ever actually gets
limited, fall back to `reauth.sh` on the `token-health.sh` cron alert.
