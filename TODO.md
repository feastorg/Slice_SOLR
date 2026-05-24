# TODO

## KiBot CI/Docs Pipeline

- DRC job: pass
- ERC job: fail (pre-DRC finds 33 DRC errors)
- Fab job: fail (pre-DRC finds 33 DRC errors)
- gen-kibot-index: skipped
- deploy-pages: skipped

### DRC Errors (33)

- clearance violations (6 errors)
- footprint_type_mismatch (1)
- drill_out_of_range: 0.2540mm actual vs 0.3000mm min (4 errors)
- starved_thermal: incomplete thermal relief (1)
- solder_mask_bridge: rear mask bridges different nets (multiple)
- unconnected_items (multiple)
