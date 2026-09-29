# Pure Heart Lists

This repo holds the live outfit/topic lists for the **Pure Heart** DDLC submod, so players get list updates the next time they start the game — no reinstall needed.

Players never touch this repo. Editing the JSON here is the whole workflow.

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
