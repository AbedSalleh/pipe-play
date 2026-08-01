# Pipe Play — Malaysian pipe combination builder

An interactive, single-file web app for planning plumbing runs with pipes and
fittings commonly sold in Malaysian hardware stores (kedai hardware) — so you
can work out exactly how parts combine **before** buying anything.

Open `index.html` in any browser. No build step, no dependencies, works offline.

## What it does

- **Real 3D canvas (WebGL, no libraries)** — pipes are actual lit cylinders in
  a scene you can orbit, zoom and pan, so above/below/vertical is never
  ambiguous. Start from a wall point, pipe stub, water tank, or a free run,
  then click the pulsing orange balls to attach the next part. Elbows and tees
  turn in the four horizontal directions **and up/down** (and can be rotated
  after placing, live in 3D). Clicking uses GPU color-picking; the engine
  (mesh generation, lighting, camera, picking) is hand-written because the
  page is fully self-contained.
- **"What do you want to combine this with?" — anything to anything** — click
  any open connection and every pipe type *and every fitting in the catalog*
  is offered **with a rendered 3D picture**; pick one and the correct chain of
  middle pieces (valve socket, reducing socket, male/female adaptors, and
  10 cm pipe stubs where two fittings can't join directly) is placed in the
  middle automatically, found by breadth-first search over the catalog. So a
  PVC line can take an HDPE elbow, a PE-AL-PE tee can meet a GI valve — the
  app works out and prices the connectors in between. Cross-material fittings
  are grouped in collapsible per-material sections to keep the panel tidy.
- **Real compatibility rules** — it only offers parts that genuinely fit the
  open connection: solvent sockets take PVC, compression fittings take HDPE,
  BSP male meets BSP female, and cross-material transitions go through the
  correct adaptors (valve socket, faucet socket, male/female adaptors,
  reducing bush, and so on).
- **Catalog** — PVC (½″/¾″/1″ solvent-weld), GI (½″/¾″/1″ threaded BSP),
  HDPE poly pipe (20/25/32 mm compression), PE-AL-PE (16/20 mm brass
  compression), PPR (20/25/32 mm heat fusion), plus taps, valves, caps and
  reducers.
- **Live shopping list** — pipes are totalled per material/size and rounded up
  to the lengths shops actually sell (5.8 m PVC, 6 m GI, 4 m PPR, per-meter
  poly), fittings are counted with the names to ask for at the counter
  (in Malay where it helps), consumables (solvent cement, PTFE tape) are added
  automatically, and a rough RM total is estimated. One click copies the list.
- **Joint guide** — short how-to for each joining method (solvent weld,
  threading with PTFE tape, compression, brass compression, PPR fusion).
- **Examples** — extend a garden tap (PVC), tank → outdoor tap (HDPE run),
  and two taps from one point (PVC tee).

Prices are rough Peninsular Malaysia estimates and vary by store — treat the
total as a budgeting guide, not a quote.

## Live page (GitHub Pages)

A workflow (`.github/workflows/pages.yml`) deploys the app to GitHub Pages on
every push. GitHub requires the site to be enabled once by the repo owner:

1. Open **Settings → Pages** on the repository.
2. Under **Build and deployment → Source**, choose **GitHub Actions**.
3. Re-run the "Deploy to GitHub Pages" workflow from the Actions tab (or push
   any commit).

After that, the app is served at **https://abedsalleh.github.io/pipe-play/**
and updates automatically on every push.
