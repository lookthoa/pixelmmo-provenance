# PixelMMO asset provenance log

Public, timestamped record proving *when* the AI-generated audio and sprites
for [LooterLand](https://looterland.site) were first created — evidence
against anyone later claiming they made one of these first, not a licence
grant to use them.

Background and the full reasoning: `PROVENANCE_PLAN.md` in the main
(private) project repo.

## What's here

- **`audio/`** — full copies of every background-music and sound-effect
  file generated for the game. Not sensitive: the game already ships these
  sounds to every player, so publishing the source file costs nothing and
  proves the exact bytes existed on this date. Filenames carry a short
  content hash (`Name.<hash12>.mp3`) so a later re-generation of the same
  track never overwrites an earlier, differently-generated one.
- **`sprite_hashes.json`** — SHA-256 hash + byte size + relative path for
  every sprite PNG, *not* the picture itself. The owner does not want the
  art handed out publicly. A hash proves nothing about what the picture
  looks like on its own, but if the picture is ever produced later —
  in a dispute, or just to double-check — its hash can be recomputed and
  compared against the one published here on this date.

## How entries get added

`tools/update_provenance.py` in the main project repo. It is re-run
automatically (see `PROVENANCE_PLAN.md`) and is safe to re-run by hand —
it only ever adds new entries, never edits or removes one, so the history
here stays an honest append-only log.
