# Design review — Md Motakabbir Rahman, 2025-03-29

Review of the rev-A board as ordered in `dda792a` (AO4882 MOSFETs,
CDBA140-G input diode, 22 µH inductor). The BQ24650 charger redesign
answers these points; this folder keeps the review as he sent it.

## Email

> Hi Cam,
>
> I have attached three documents highlighting some minor issues with the design and one datasheet:
>
> 1. I identified two issues in the schematic interconnection, which I have marked.
> 2. There are concerns regarding the diode, inductor, and series current measuring resistor ratings. These components should be rated for the charging current range (0–8A). However, in the current design, the inductor is limiting the maximum charging current to 200mA, the diode to 1A and the resistor to 500mA. I have marked the high-current path and the components.
> 3. As mentioned earlier, the trace width needs adjustment based on the maximum charging current. In its current form, I don’t believe it can handle more than 500mA, as I indicated in the attached picture. I have also attached a reference traced width and board design from the BQ24650 solar charger evaluation board by Texas Instruments, along with its datasheet. Reviewing this reference design may be beneficial.
> 4. I think first you need to finalize the target maximum charging current. Based on my estimate, a 25W–30W PV should be enough for the bread system, leading to a maximum current of ~4A for an 8V battery (or lower for higher-voltage batteries). The diode, inductor, current measuring resistor, and trace width should be designed accordingly. In its current form, the system can support maximum of 500mA (~5W PV input) maximum.
>
> Additionally, I have not used this IC before, so these are my observations. We can discuss further if needed.
>
> Regards
> Motakabbir

## Attachments

| File | Sent as | Contents |
| --- | --- | --- |
| [`schematic-interconnection.pdf`](schematic-interconnection.pdf) | Issue in schematic interconnection.pdf | Point 1, marked on the rev-A schematic |
| [`component-selection.pdf`](component-selection.pdf) | Issue in component selection.pdf | Point 2: high-current path and its ratings, marked |
| [`trace-width-vs-evm.png`](trace-width-vs-evm.png) | inline image | Point 3: rev-A layout against the EVM top layer, annotated |
| not committed (TI copyright) | Solar charger demo board BQ24650 by TI.pdf | TI SLUU444A, the BQ24650EVM user guide: <https://www.ti.com/lit/ug/sluu444a/sluu444a.pdf> |

## Notes on the marked-up schematics

Transcribed from his annotations, to make them searchable.

Schematic interconnection:

- Bootstrap: "A shotkey diode between REGN and BTST. BTST should be
  connected to D2 terminal. Or use a single shotkey diode between REGN and
  BTST." (marked on D2, BAT54C)
- "Bootstrap capacitor should be connected to PH." (marked on C5)
- Sense resistor, next to the datasheet's §8.3.3 equation
  (I = 40 mV / R_SR): "500mA (max) with 80mohm, for 2A charging — 20mOhm or
  less".
- L2: "0805 inductor typically (50mA–300mA)".

Component selection — the path SolarIn → D3 → HIDRV_D → Q1A → L2 → R7 →
BatteryOut is marked as carrying up to 8 A. D3 (CDBA140-G) is circled as
"40v 1a".
