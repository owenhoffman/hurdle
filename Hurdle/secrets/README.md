# Echole

A single-file, audio-first word-guessing game in the spirit of Wordle — guess the
5-letter word in 6 tries, but instead of colored tiles you *hear* the result of
each guess:

- **Coin-style ding** — right letter, right spot
- **Neutral tone** — letter's in the word, wrong spot
- **Dud thunk** — letter isn't in the word

Colors can optionally be revealed for sighted play, and results can be
announced as text for screen readers.

## Running it

Open [`hurdle.html`](./hurdle.html) directly in a browser — no build step or
server required.

## Controls

- Type letters, `Backspace`, and `Enter` to play.
- Press `1`–`6` to replay the sounds for a submitted row.
