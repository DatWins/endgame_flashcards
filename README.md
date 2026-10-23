# Endgame Flashcards

Real chess endgame finishes pulled from Lichess games (via `pgnslim`/`pawnend`),
shown as a flip card: a board you can try, or open on Lichess to play against
their engine — flip it to see how the real game ended.

Built with Hugo (hugo-scroll theme), deployed to GitHub Pages.

## Adding games

Each category's real games live in `static/data/<category>.json` as an array
of objects:

```json
{
  "site": "https://lichess.org/xxxxxxxx",
  "event": "Rated Classical game",
  "white": "name", "black": "name",
  "whiteElo": 1183, "blackElo": 1058,
  "startFen": "<FEN at the first moment the position matches this category>",
  "moves": ["h3", "e8=Q", "h2", "Qh5"],
  "result": "1-0"
}
```

A page picks one at random from its category's file each time it loads
(client-side), with a Shuffle button for another. An empty `[]` means no
games have been added yet for that category.
