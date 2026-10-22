# SPIEL 26 booth demo booking

One page: `index.html` (vanilla HTML/JS, no build). Team books demo slots at two tables, Oct 22–25 2026.

- Data: Supabase project "Board Game Creator" (`xzmtgdapqbitsqmymict`), table `public.spiel26_docs(path text pk, data jsonb)`.
  Paths: `bookings/<id>` and `team/members`. RLS is open to anon on this table only, on purpose: anyone with the page can book without an account.
- The page uses the publishable key via plain `fetch` to PostgREST and polls every 4 s.
- Live page: https://slowfacemusic.github.io/spiel26-booth/ (GitHub Pages, main / root). Old link: claude.ai artifact https://claude.ai/artifact/4ZEZcu8H6MvPmaEbaBxd3P (now only links to GitHub Pages).
- Local preview: `.claude/launch.json` → `booth` (python http.server on 8765). Don't save test bookings, it is the live database.
