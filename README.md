# ECE 4530 Lab 3

Cadence Virtuoso library for Lab 3. This whole folder is one Cadence library
named **`lab3`**.

## Contents

| Path | What it is |
| --- | --- |
| `Lab3_dummy/` | Verilog-A model (`veriloga`), with its schematic and symbol |
| `lab3_v1/` | Lab 3 circuit (schematic + symbol) |
| `lab3_testbench/` | Testbench for `lab3_v1` (schematic + Maestro setup) |
| `step1/` | Plots from the `Lab3_dummy` Verilog-A simulations |
| `cdsinfo.tag`, `.oalib`, `data.dm` | Cadence library files. Leave these alone. |

## Setup

1. Clone the repo next to your other Cadence libraries (the folder that has your `cds.lib`):

   ```
   cd ~/ece4530
   git clone https://github.com/zoeeechiu/analog-lab3 lab3
   ```

2. Add this line to your `cds.lib`, using the full path to the folder you just cloned:

   ```
   DEFINE lab3 /home/<netid>/ece4530/lab3
   ```

   The library name must be `lab3`, because the schematics refer to their cells
   as `lab3/...`. The folder itself can be called anything.

3. Restart Virtuoso, or use View -> Refresh in Library Manager. `lab3` should show up.

4. Before the first simulation, open `lab3_testbench/schematic` and run
   **Check and Save** (Shift+X). Then run `lab3_testbench/maestro`.

## Workflow

```
git pull                      # before you start working
# ...make changes in Cadence, then Check and Save...
git add .
git commit -m "Describe what you changed"
git push
```

- Save (or close) a cellview in Cadence before committing it.
- `.oa` files are binary, so git cannot merge them. If two people edit the same
  cellview at the same time, one person's changes get lost. Coordinate before
  editing a shared cell, or make your own copy with your NetID in the name.
- `.gitignore` keeps Cadence lock files (`*.cdslck*`), `.bak` files, and
  Maestro `results/` and `history/` folders out of the repo.
