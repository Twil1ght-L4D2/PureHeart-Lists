# Pure Heart Lists

This repo holds the live outfit/topic lists for the **Pure Heart** DDLC submod, so players get list updates the next time they start the game — no reinstall needed.

Players never touch this repo. Editing the JSON here is the whole workflow.

## How to update the lists

1. Edit `pureheart_lists.json`:
   - **Add an outfit to keep**: add its id to `keep`.
   - **Ban one**: add it to `block` (and add a `replace` entry so Monika changes into something wholesome).
   - **Ban a topic or greeting**: add its label to `events` or `greetings`.
   - **New lewd-sounding pack**: add a word to `words` — any outfit id containing it is auto-removed.
2. Bump `version` (e.g. `2.0` → `2.1`). Installs only apply a *higher* version.
3. Commit. Everyone gets the update at their next game launch.

## How the game fetches it

Raw URL (used by the submod):

```
https://raw.githubusercontent.com/Twil1ght-L4D2/PureHeart-Lists/refs/heads/main/pureheart_lists.json
```

Raw URLs can lag a few minutes after a push due to GitHub's CDN — that's normal, the next launch gets it.

## Safety rules

- The submod validates the file every time: wrong shape, empty lists or absurd sizes are ignored, and the previous lists stay in effect.
- The word filter always runs on top — even a bad `keep` entry can't reintroduce anything lewd-named.
- Offline? The game keeps working from `ph_lists_cache.json` (last good download) or the lists built into the submod.
- The loader's own lists are separate; sync them manually when you release a new loader build.
