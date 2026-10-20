# Campus Network Architecture

## 1. Context and Requirements

Atlas Industrie needs a reliable network connecting two buildings. The design must provide VLAN segmentation, inter-building connectivity, redundancy, and controlled costs.

## 2. Technical Targets Retained

- 10 access switches (48-port PoE+).
- Firewall pair.
- VLANs and IPv4 networks defined in the IP plan.
- Fibre connectivity between the two buildings.
- Five-year cost comparison.

## 3. The Three Architectures Compared

| Architecture | Equipment | Main characteristic |
|---|---|---|
| S1 – Three-tier | 2 modular cores, 4 distribution switches, 10 access switches, firewall pair | More equipment and higher cost |
| S2 – Distributed collapsed core | 2 fixed cores, 10 access switches, firewall pair | One core per building |
| S3 – Single-site collapsed core | 2 fixed cores, 10 access switches, firewall pair | Both cores in Building A |

## 4. Five-Year Costing

All amounts are in MAD. Support is 10% of CAPEX per year. Operations cost 1.5 days per device per year at 5,400 MAD/day. Power and cooling are excluded.

### 4.1 CAPEX

| Equipment | S1 | S2 | S3 |
|---|---:|---:|---:|
| Core switches | 324,000 | 172,800 | 172,800 |
| Distribution switches | 216,000 | 0 | 0 |
| Access switches | 270,000 | 270,000 | 270,000 |
| Firewall pair | 216,000 | 216,000 | 216,000 |
| Fibre and optics | 129,600 | 108,000 | 86,400 |
| **Total CAPEX** | **1,155,600** | **766,800** | **745,200** |

### 4.2 Five-Year TCO

| Cost | S1 | S2 | S3 |
|---|---:|---:|---:|
| CAPEX | 1,155,600 | 766,800 | 745,200 |
| Support over 5 years | 577,800 | 383,400 | 372,600 |
| Operations over 5 years | 729,000 | 567,000 | 567,000 |
| **Five-year TCO** | **2,462,400** | **1,717,200** | **1,684,800** |

**Calculations**

- Annual support = CAPEX × 10%.
- Five-year support = annual support × 5.
- Annual operations = number of devices × 1.5 × 5,400.
- Five-year operations = annual operations × 5.
- TCO = CAPEX + five-year support + five-year operations.

## 5. Decision and Justification

**S2 is recommended.** Compared with S1, it saves **745,200 MAD** over five years. Compared with S3, it costs only **32,400 MAD more** over five years.

At 108,000 MAD per hour of downtime, this additional cost is equivalent to **18 minutes of downtime**. S2 is preferred because each building has its own core, reducing dependence on a single building.

## 6. Risks and Points of Failure

- Fibre routes may share a common point of failure.
- A power failure may affect network equipment.
- Access switches are not necessarily redundant.
- S3 concentrates both cores in Building A.
- Full availability cannot be guaranteed by equipment redundancy alone.

## 7. Assumptions and Limits

- Costs are estimates based on the prices provided in the lab.
- Power and cooling costs are excluded.
- Fibre route separation, technical-room locations, and UPS arrangements must be verified.
- Any assumed physical details must be clearly identified as assumptions.
- The design does not guarantee 99.99% availability.