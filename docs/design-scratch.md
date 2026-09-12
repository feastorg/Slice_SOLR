# Design Scratch

Working notes for the charger redesign. Not part of the published docs site
(excluded in `_config.yml`).

## References

- BQ24650 datasheet: <https://www.ti.com/lit/ds/symlink/bq24650.pdf>
- BQ24650EVM-639 user guide (reference design): <https://www.ti.com/lit/ug/sluu444a/sluu444a.pdf>
- BQ24650EVM-639 design files: <https://www.ti.com/tool/BQ24650EVM-639#design-files>
- BQ24650 product page: <https://www.ti.com/product/BQ24650#design-development>

## Components

- ZLLS350TA — Schottky, 40 V 380 mA, SOD-523 (bootstrap diode, REGN → BTST)
  - <https://www.digikey.ca/en/products/detail/diodes-incorporated/ZLLS350TA/991168>
- PDS1040-13 — Schottky, 40 V 10 A, PowerDI 5
  - <https://www.digikey.ca/en/products/detail/diodes-incorporated/PDS1040-13/697100>
- SI7288DP-T1-GE3 — dual N-channel MOSFET, 40 V 20 A, PowerPAK SO-8
  - <https://www.vishay.com/docs/65366/si7288dp.pdf>
