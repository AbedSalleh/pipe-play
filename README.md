# Pipe Play — Malaysian pipe combination builder

An interactive, single-file web app for planning plumbing runs with pipes and
fittings commonly sold in Malaysian hardware stores (kedai hardware) — so you
can work out exactly how parts combine **before** buying anything.

Open `index.html` in any browser. No build step, no dependencies, works offline.

## What it does

- **Snap-together 3D canvas (isometric)** — start from a wall point, pipe stub,
  water tank, or a free run, then click the orange dots to attach the next
  part. The scene is true 3D drawn as a plumber's isometric: elbows and tees
  can turn in the four horizontal directions **and up/down**, so risers,
  standpipes and drops render properly. Parts above the floor cast a soft
  shadow on the ground plane so height reads at a glance, and vertical runs
  are labelled with ↑/↓.
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
