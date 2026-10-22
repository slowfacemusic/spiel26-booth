# SPIEL 26 booth demo booking

One page: `index.html` (vanilla HTML/JS, no build). Team books demo slots at two tables, Oct 22–25 2026.

- Data: Supabase project "Board Game Creator" (`xzmtgdapqbitsqmymict`), table `public.spiel26_docs(path text pk, data jsonb)`, no direct anon access.
  Paths: `bookings/<id>` and `team/members`. The page reaches it only via rpc `spiel26_read/write/delete(code, ...)`, which check a team code. The code lives only in the DB function `spiel26_check`, never in this repo.
- The page uses the publishable key via plain `fetch`, asks for the team code once (localStorage), polls every 4 s.
- Live page: https://slowfacemusic.github.io/spiel26-booth/ (GitHub Pages, main / root). Old link: claude.ai artifact https://claude.ai/artifact/4ZEZcu8H6MvPmaEbaBxd3P (now only links to GitHub Pages).
- Local preview: `.claude/launch.json` → `booth` (python http.server on 8765). Don't save test bookings, it is the live database.
