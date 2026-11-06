# SIPOC: SECOM Semiconductor Production Line

A high-level map of the process this project studies.

*The SECOM data is anonymized, so the exact process steps are not known.
The steps below are the typical main steps of a semiconductor wafer fab.
They repeat many times as layers are built up.*

| Suppliers | Inputs | Process | Outputs | Customers |
|---|---|---|---|---|
| Silicon wafer suppliers | Bare silicon wafers | 1. Deposition | Tested units (pass or fail) | Downstream assembly and packaging |
| Gas and chemical suppliers | Process gases and chemicals | 2. Photolithography | 590 process signals per unit | Yield and process engineers |
| Mask makers | Photomasks (circuit patterns) | 3. Etching | Scrapped units (failures) | End customers (chip buyers) |
| Equipment vendors | Process tools and their settings (recipes) | 4. Doping (implant or diffusion) | | Quality and operations managers |
| Utilities | Power, ultrapure water | 5. Polishing and cleaning | | |
| Fab staff | Operators and technicians | 6. In-house final test | | |

## Process boundaries

- **Starts:** a bare wafer enters the line.
- **Ends:** the unit receives a pass or fail result at in-house final test.

## Link to this project

- The **590 process signals** are measured during steps 1 to 5.
- The **pass/fail result** comes from step 6.
- This project looks for links between the two.