# tracku

a calm, creative-friendly personal front door to [Linear](https://linear.app).
hot pink, a pixel cat, chunky pill cards — the pretty window you actually want
to open each morning. ticking something done is the most satisfying pixel in the app.

## what it is

one self-contained `index.html`. two data layers:

- **Linear** is the source of truth for issue content (title, status, who, when,
  project, comments, attachments). read live, written back.
- a small **local layer** in your browser holds the *vibe* stuff Linear never sees:
  which bucket a card is in (today / tomorrow / backlog), and your shipped tally.

your Linear API key is entered in the browser and stored only on your device
(`localStorage`) — it is never in this code and never committed. it only ever
travels to `api.linear.app`.

## run it locally

```sh
node serve.js       # then open http://localhost:4173
```

`serve.js` is a tiny static server for local development only — it is not used
when the site is hosted (a host just serves `index.html` directly).

## deploy

it's a static site. point any static host at the folder; `index.html` is the
entry. on [Vercel](https://vercel.com): import the repo, no build step, no config.

## connecting Linear

open the app → paste a personal API key
(Linear → Settings → Security & access → Personal API keys) → pick your team.
on first connect your issues land in the **backlog** shelf; pull today's picks up
each morning.
