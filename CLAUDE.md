# fused-render app

This folder is a **fused-render app** — a self-contained folder rendered by
the fused-render explorer. `index.html` is the app's entry view; it was
scaffolded from the starter kit, so edit it in place (don't create a second
top-level `.html` next to it — one entry file is what makes the folder open
as an app).

The page runs inside the explorer, which injects a `fused` runtime bridge:
`fused.params` (URL-synced view state), `fused.runPython("./file.py", args)`
(compute in Python files beside this one), `fused.readFile` / `fused.rawUrl`,
and more. There is no network at runtime and no build step.

Before non-trivial changes, invoke the **`fused-render-authoring`** skill —
the full contract for `.html` views and `.py` data files: the `fused` bridge,
params-as-state wiring, file IO, theming, and debugging blank views /
traceback overlays.

## Version control

This folder lives inside the workspace apps repository — one local git repo
at the parent `local/` folder, shared by every app beside this one (the
starter landed as this folder's first commit). **Commit as you work, in small
chunks** — after every coherent change, even tiny ones (a copy tweak, a
single style fix, one function). Never batch a whole task into one commit,
and never leave this folder dirty at the end of a turn.

**Always scope git to this folder.** Stage with `git add -A -- .` and commit
with `git commit -m "…" -- .`, run from this directory. Never run a bare
`git add -A`, `git commit -a`, or an unscoped `git commit` — sibling apps
share the repository, and an unscoped command sweeps their in-progress work
into your commit. (`git status -- .` and `git log -- .` are the scoped reads.)
Use short imperative subjects ("Add dark theme toggle", "Fix param sync").
Don't push, don't add remotes, don't rewrite history, don't touch paths
outside this folder — the repo is purely local undo history for the apps.

fused-render installs that skill (and its siblings, `fused-render-usage` and
`fused-render-custom-templates`) into Claude Code's user-level skills
directory and keeps them up to date, so it is available here by name. If the
skill isn't listed, start (or restart) fused-render once — the server
re-installs it on startup.
