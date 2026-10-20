# Atlas Industrie–- network architecture repository
Design of the Atlas Industrie network, the fictitious company of the
"Advanced Network Architectures" course. One folder per object type;
the addressing plan is authoritative in `data/vlans.yml`.
Local check: `python3 scripts/check_vlans.py` from the repository root.
IPv6 ULA prefix of the project: fd11:9261:9036::/48 (RFC 4193). Do not change it.
## What the check does not do
`scripts/check_vlans.py` detects duplicate VLAN identifiers and IPv4/IPv6 overlaps.
It does not validate mandatory fields, nor the consistency between VLAN, zone and subnet
(a VLAN placed outside its zone block is not detected).