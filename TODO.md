# TODO

## Redesign — schematic

- [x] Rebuild charger stage from the BQ24650 datasheet and EVM-639 reference design
- [x] All symbols resolve from KiCad-Master-Lib (no `*-rescue` / `kml-custom` references)
- [x] ERC clean (`kicad-cli sch erc --severity-all`: 0 violations)
- [ ] Design review of the schematic against the EVM-639 BOM (MPPSET divider, sense resistor, inductor, TS network)

## Redesign — layout

- [ ] Assign footprints to `NT1` (`NetTie_2`) and `JP1` (`Jumper_3_Open`)
- [ ] Place and route the board (PCB currently holds only the Nano socket, buck stage and mechanicals; nothing routed)
- [ ] Clear DRC schematic parity (66 missing footprints, 3 net conflicts, 1 extra footprint at last run)
- [ ] Clear DRC (4 unconnected items; 36 silk-to-edge, 6 silk-over-copper, 4 silk-overlap, 4 isolated-copper warnings)
- [ ] Confirm board outline and mounting holes against the slice standard

## Pre-fab

- [ ] Verify BOM sourcing (KiBot `BoM/` outputs)
- [ ] Footprint verification against datasheets
- [ ] Design review sign-off
