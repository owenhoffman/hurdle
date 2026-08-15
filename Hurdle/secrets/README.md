# Echole

A word-guessing game in the spirit of Wordle, built to be played by ear. The
screen is black by default — instead of colored tiles, each guess plays a
sound per letter:

- **Coin-style ding** — right letter, right spot
- **Neutral tone** — letter's in the word, wrong spot
- **Dud thunk** — letter isn't in the word

Guess the word in 6 tries to advance to the next level. There are 25 levels
in all; level 1 is always `START`, and levels 20–25 spell out `MATCH THEME
WORDS GREEN SHORT RESET`. The rest of the levels are chosen fresh — some
randomly from the answer word list, and some as a fixed set of secret
levels (see below). All 25 answers are picked at the start of each game and
re-picked whenever you reset, so no two playthroughs land the same way.

## Running it

Open [`index.html`](../index.html) directly in a browser — no build step or
server required.

## Controls

- Type letters, `Backspace`, and `Enter` to play.
- Press `1`–`6` to replay the sounds for a submitted row.

## Secrets

A handful of words do something other than get scored as a normal guess
when you type them and press `Enter`:

- **`DEBUG`** — toggles the screen between black (default) and visible.
  Tile colors, and any level-start sound effects, only ever show/play once
  the screen is visible.
- **`EXPAND`** — permanently switches the grid to 6-letter words for the
  rest of the session.
- **`RESET`** — jumps back to level 1 and re-rolls which levels get which
  secret words.
- **`SKIPS`** — skips ahead to the next level. Only works while the screen
  is visible (i.e. `DEBUG` is on).

Twelve of the levels between 2–19 are special every game, though which
twelve — and in what order — changes every time:

- Six of them use `QUACK`, `SWISH`, `BLEEP`, `VROOM`, `WHIZZ`, and `BOING`
  directly as the level's answer.
- The other six pick a real answer word that matches a specific
  letter-feedback pattern against one of those six words, and play that
  word's sound effect the moment the level starts.

Open the browser console to see exactly how a given playthrough's levels
were assigned — `window.FIXED_LEVEL_WORDS` lists the answer for every
level, and `window.LEVEL_START_SOUNDS` lists which levels play a sound.
There's also a `findPatternMatches(guess, pattern)` helper for exploring
which words produce a given feedback pattern against a guess.
