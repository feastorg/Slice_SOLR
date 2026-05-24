# TODO

## Pass 1 — CI Pipeline

- [x] Pipeline added
- [x] DRC: FAIL — 33 errors (clearance, footprint_type_mismatch, drill_out_of_range, starved_thermal, solder_mask_bridge, unconnected_items)
- [x] ERC: PASS
- [ ] Fab: SKIPPED (blocked by DRC pre-flight)
- [ ] gen-kibot-index: SKIPPED
- [ ] deploy-pages: SKIPPED

### DRC Errors (33)

- clearance violations (6)
- footprint_type_mismatch (1)
- drill_out_of_range: 0.254mm actual vs 0.300mm min (4)
- starved_thermal: incomplete thermal relief (1)
- solder_mask_bridge: rear mask bridges different nets (multiple)
- unconnected_items (multiple)

## Pass 2 — Pre-Fab Review

- [ ] Fix 6x clearance violations
- [ ] Fix 1x footprint type mismatch (expected SMD, got TH)
- [ ] Fix 4x drill out of range (increase drill diameter to ≥0.3mm)
- [ ] Fix 1x starved thermal relief
- [ ] Fix solder mask bridge errors
- [ ] Fix unconnected items
- [ ] Verify BOM completeness and sourcing
- [ ] Confirm board outline and mounting holes
- [ ] Footprint verification against datasheets
- [ ] Design review sign-off
