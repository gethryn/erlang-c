# Erlang C, in every language

A small public reference for the **Erlang C** call-centre staffing formula:
a live calculator, the maths, and clean, self-contained implementations in
**30 programming languages** — free to copy, verified against known values.

**Live site → https://gethryn.github.io/erlang-c/**

The page is a single self-contained `index.html` (no build step, no dependencies,
works offline). Open it locally or host it anywhere.

## What's inside

- **A live calculator** — offered call load + a service-level target → the number
  of agents you need, with the achieved service level, ASA, occupancy and
  probability-of-wait around that staffing point.
- **The maths** — traffic intensity, the Erlang C wait probability, service level,
  average speed of answer (ASA), occupancy, and the agents-required search.
- **The code** — the same five functions in each of:
  JavaScript · TypeScript · Python · R · C · Go · Rust · Ruby · Java · C# ·
  Swift · Kotlin · Scala · F# · Clojure · Haskell · Elixir · Lua · Dart · Nim ·
  Zig · Fortran · Objective-C · PHP · Julia · Perl · VBA · SQL · MATLAB/Octave ·
  Excel formulas.

## Numerically stable by construction

Naive factorials overflow past ~170 agents. Every implementation computes the
Poisson terms in log-space using a bundled **Lanczos `lgamma`** (matched to the
platform's own `lgamma` to ~1×10⁻¹³), so results stay exact at any centre size
and depend on nothing but the standard maths library.

Worked example used to verify every port: **100 calls / 30 min, 180 s AHT,
80% answered within 20 s → 14 agents.**

## Background

Agner Krarup **Erlang** derived this at the Copenhagen Telephone Company in 1917
to size manual switchboards. It still staffs every contact centre with a queue.

## Licence

**CC0 1.0 — public domain.** No rights reserved. Take it, port it, ship it.
Corrections and new-language ports welcome.
