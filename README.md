[README.md](https://github.com/user-attachments/files/31056820/README.md)
# Kickoff Cup

A solo, dice-driven football tournament game that runs entirely in the browser. Draw a random field of national teams, play the group stage, and knock your way through to a champion — deciding every result yourself, by hand or with the dice.

It's a single HTML file with no build step, no server, and no dependencies to install. Just open `index.html`.

## Play it

```
https://bielkebielke.github.io/Oskandowski-cup/
```

If hosted on GitHub Pages, it lives at:

```
https://YOUR-USERNAME.github.io/kickoff-cup/
```

Or download `index.html` and open it in any modern browser.

## How it works

- **Pick a size.** 32 teams (8 groups) or 64 teams (16 groups). The field is drawn at random from the pool of national teams.
- **Group stage.** Round-robin groups of four; top two advance. Standings are ranked by points, then goal difference, then goals scored.
- **Score results your way.** Type them in by hand (any number), or roll for them.
- **Knockout.** Standard bracket through to the final.
- **Champions history.** The first edition is World Cup 2028, then every four years with no end. Each winner is recorded in the Hall of champions.

## The dice

- **d4 — the goal die.** Sets each side's goals in a match (0–3). Also used in extra time: a roll of 1 scores.
- **Hidden d6 — the bonus die.** Roll a 3 on the d4 and a hidden d6 rolls behind the scenes. Each 6 grants a bonus goal, chaining on further 6s. You only ever see the final score. Hard cap: 9.
- **d20 — the golden chance.** For a knockout tie still level after extra time, each team rolls a d20. Only a 20 scores.

### Level knockout tie

Resolved in order: **extra time → d20 golden chance → penalty shootout**, until someone wins.

## Keyboard shortcuts (dice mode)

- **N** — jump to the next unplayed match or tie.
- **D** (or Enter / Space) — roll / take a kick while the dice popup is open.

## Saving

Progress saves automatically in your browser (per browser, per device). Use **Export save** to download a `.json` file, and **Import save** to load it elsewhere — handy for moving between devices or keeping a backup.

## Notes and limitations

- Flags are rendered via [Twemoji](https://github.com/twitter/twemoji), loaded from a CDN, so they display consistently across platforms (Windows has no built-in colour flag emoji). This means the page needs an internet connection to show flag images; without it, flags fall back to their two-letter codes.
- Browser storage can be cleared by the browser or the user, so export a save if you want to keep it.
- "All teams in the pool" currently draws from a fixed list of national teams. Some teams that share a flag emoji (e.g. Wales and Scotland) will show the same flag.

## Planned / ideas

- Other competitions (European, Copa América, African, Asian, and domestic leagues), unlockable, with the World Cup as the starting point.
- Unlockable dice skins (disco, starry, pink, flag, and more).
- Hand-drawn maps in place of flags in a later version.

## Tech

Plain HTML, CSS, and JavaScript in one file. No frameworks, no build. Cryptographically-backed randomness (`crypto.getRandomValues`) for the draw and dice.
