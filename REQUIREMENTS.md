# Electrical System Diagram Requirements

## Tool
- diagrams.net (draw.io)
- File format: `.drawio` XML

## No Print Target
- Use as much space as you need.

## Wire Routing

### Connectors
- Use `source` and `target` attributes on edges to connect to object IDs
- Use `edgeStyle=orthogonalEdgeStyle` for right-angle wire routing
- This allows wires to follow objects when repositioned

### Layering
- Never run wires over or under an object. The must run between objects
- In diagrams.net XML, elements defined later are drawn on top
- Structure: Define ALL edges (wires) first, then ALL vertices (objects)

### Overlap Rules
- Same wire types may overlap (e.g., positive on positive is OK)
- Different wire types should NOT overlap (e.g., positive crossing data wires)
- Separate power and data sections to minimize crossings

## Wire Color Coding

### Power
| Wire Type | Color | Stroke Width | Style |
|-----------|-------|--------------|-------|
| 12V Positive | Red (#CC0000) | 3 | Solid |
| Ground (-) | Black (#000000) | 3 | Solid |
| Control | Green (#82b366) | 2 | Solid |

### Data
| Wire Type | Color | Stroke Width | Style |
|-----------|-------|--------------|-------|
| NMEA0183 | Blue (#0000FF) | 2 | Dashed |
| N2K | Green (#00AA00) | 2 | Dashed |
| NKE Topline | Red (#b85450) | 2 | Dashed |
| Bluetooth/Wifi | Purple (#9673a6) | 2 | Dashed |
| Charging Data | Gold (#d6b656) | 2 | Dashed |

## Component Styling

| Component | Shape | Fill Color | Stroke Color |
|-----------|-------|------------|--------------|
| Battery | cylinder3 | #fff2cc | #d6b656 |
| Bus Bar (+) | rectangle | #f8cecc | #b85450 |
| Bus Bar (-) | rectangle | #000000 | #000000 |
| Switch | rectangle | #d5e8d4 | #82b366 |
| Fuse | rectangle | #ffe6cc | #d79b00 |
| Shunt | rectangle | #e1d5e7 | #9673a6 |
| Load | rectangle | #fff2cc | #d6b656 |
| Panel | rectangle | #ffe6cc | #d79b00 |
| Smart Device | rectangle | #dae8fc | #6c8ebf |
| Charging Source | rectangle/ellipse | #d5e8d4 | #82b366 |

## Layout Organization

### Power Section (Left)
- House Bank: Batteries, bus bars, fuses, switches, shunts
- Starter Bank: Battery, bus bars, fuse, switch, engine starter
- Parallel switch and echo charger between banks
- Charging sources: Alternator, solar controllers, hydro generator
- Distribution panels
- Load circuits

### Data Section (Right)
- Separate boxed area for data networks
- Group by type: Wireless, Charging Data, Navigation Data, NKE Topline
- Use text labels to show device connections instead of cross-diagram wires

## Circuit Topology Notes
Per INVENTORY.md:
- (+) Circuit: All positive loads must pass through (+) shunt
  - Flow: House (+) Bus → Fuse → Switch → Shunt (+) → Loads
- (-) Circuit: All negative loads must pass through (-) shunt AND SmartShunt in series
  - Flow: House (-) Bus → Shunt (-) → SmartShunt → Neg Dist Bus → Loads
