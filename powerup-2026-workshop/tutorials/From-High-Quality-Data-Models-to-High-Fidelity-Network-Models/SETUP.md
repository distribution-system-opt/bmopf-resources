# Setting up the environment (no Julia experience needed)

This guide takes you from *nothing installed* to *the tutorial notebook running*, with
copy-paste commands for **Linux**, **Windows** and **macOS**. You should not need any
prior knowledge of Julia. Please do this **before** the workshop — the first install
downloads and compiles a lot and can take 10–20 minutes.

**What you'll end up with:** Julia installed, a self-contained project environment
holding the tutorial's packages, and
`From-High-Quality-Data-Models-to-High-Fidelity-Network-Models.ipynb` open in Jupyter.

---

## Step 1 — Install Julia

We use **`juliaup`**, the official Julia version manager. It installs the `julia`
command and keeps it up to date.

### Linux

```bash
curl -fsSL https://install.julialang.org | sh
```

Accept the defaults. When it finishes, **close the terminal and open a new one**.

### macOS

```bash
curl -fsSL https://install.julialang.org | sh
```

Accept the defaults, then **close the terminal and open a new one**.

### Windows

In a terminal (PowerShell or Command Prompt):

```powershell
winget install julia -s msstore
```

(Or search for **"Julia"** in the Microsoft Store and install it there.) Then **open a
new terminal**.

### Check it worked

In a **new** terminal:

```bash
julia --version
```

You should see `julia version 1.11` or newer. The notebook was built with Julia 1.11,
so anything from 1.11 upward is fine.

> **`julia` not found?** Close and reopen the terminal. On Windows, log out and back in
> once. If you can't use `juliaup` (e.g. a locked-down machine or a proxy that blocks
> the script), download an installer from
> <https://julialang.org/downloads/> instead — pick the current stable release.

---

## Step 2 — Get the tutorial files

Either clone the repository with `git`:

```bash
git clone https://github.com/frederikgeth/bmopf-report
```

…or, if you don't have `git`, open
<https://github.com/frederikgeth/bmopf-report>, click **Code ▸ Download ZIP**, and
extract it.

Now move into the tutorial folder.

### Linux / macOS

```bash
cd bmopf-report/powerup-2026-workshop/tutorials/From-High-Quality-Data-Models-to-High-Fidelity-Network-Models
```

### Windows (PowerShell)

```powershell
cd bmopf-report\powerup-2026-workshop\tutorials\From-High-Quality-Data-Models-to-High-Fidelity-Network-Models
```

This folder contains `Project.toml`, which lists the packages the tutorial needs.

---

## Step 3 — Install the packages

Start Julia **inside that folder** with the project activated:

```bash
julia --project=.
```

`--project=.` tells Julia to use the environment described by the `Project.toml` in the
current folder, kept separate from your global setup.

At the `julia>` prompt, press **`]`**. The prompt changes to `pkg>` (the package
manager). Run these two commands:

```julia-repl
pkg> add https://github.com/frederikgeth/BMOPFTools.jl
pkg> instantiate
```

- `add https://github.com/frederikgeth/BMOPFTools.jl` installs `BMOPFTools` (it is not
  in Julia's public package registry, so it has to be added by URL). This also pulls in
  the other packages listed in `Project.toml` — `JuMP`, `Ipopt` and `IJulia`.
- `instantiate` makes sure everything else is downloaded and built, including the
  `Ipopt` solver binaries.

This step does the heavy downloading and precompiling — give it a few minutes.

When it's done, press **Backspace** to return to the `julia>` prompt. Keep this Julia
session open for Step 4.

---

## Step 4 — Open the notebook

Pick **one** of the following.

### Method A — Jupyter via IJulia (recommended, nothing extra to install)

In the same `julia --project=.` session, at the `julia>` prompt:

```julia-repl
julia> using IJulia

julia> notebook(dir=pwd())
```

The first time, IJulia asks whether to install a private copy of Jupyter — answer
**`y`**. A browser tab opens showing the folder contents. Click
`From-High-Quality-Data-Models-to-High-Fidelity-Network-Models.ipynb`. If prompted for
a kernel, choose **Julia**.

(Prefer JupyterLab? Use `jupyterlab(dir=pwd())` instead of `notebook(dir=pwd())`.)

### Method B — VS Code (if you already use it)

1. Install [VS Code](https://code.visualstudio.com/), then add its **Julia** and
   **Jupyter** extensions from the Extensions panel.
2. Open the tutorial folder in VS Code (**File ▸ Open Folder…**) and open the
   `.ipynb` file.
3. Click **Select Kernel** (top right) and choose the **Julia** kernel.
4. You still need to have run **Step 3** first so the packages exist.

---

## Step 5 — Check everything is ready

Run the first code cell of the notebook (or type this at a `julia>` prompt started with
`julia --project=.` in the tutorial folder):

```julia
using JuMP, Ipopt
import BMOPFTools as _BM
```

If that runs with no error, you're set for the workshop.

---

## Troubleshooting

- **`julia` not found** — open a fresh terminal; on Windows, log out and back in.
- **`BMOPFTools` (or `JuMP`/`Ipopt`) not found in the notebook** — the notebook is
  running in the wrong environment. Make sure you started Jupyter from a
  `julia --project=.` session in the tutorial folder (Method A does this for you). In a
  running notebook you can check by running `import Pkg; Pkg.status()` — you should see
  `BMOPFTools`, `JuMP`, `Ipopt` and `IJulia` listed.
- **`add https://…BMOPFTools.jl` fails** — check your internet connection / proxy, then
  re-run it. It must be run from `julia --project=.` in the tutorial folder.
- **Start over** — delete the `Manifest.toml` file in the tutorial folder and repeat
  Step 3.
- **Corporate proxy blocking the install script** — use the Microsoft Store method
  (Windows) or the installer from <https://julialang.org/downloads/>.
