# Internet & Network

**Status:** Active

## Scheduled
- **6/27/2026 (tomorrow)** — Cable modem installation (cable company technician)

## Phase 1 — Cable Modem Install (6/27)
- [ ] Be home for technician
- [ ] Confirm installation location for modem (ideally near central wiring point)
- [ ] Get account number and support contact from tech
- [ ] Test speeds after install

## Current State
- UCG Ultra and all devices (except U6 Pro AP) connected over WiFi
- U6 Pro access point is wired

## Phase 2 — Own Network Setup
- [ ] Connect own router to cable modem
- [ ] Configure router (SSID, password, firewall settings)
- [ ] Decide on network topology (flat, VLANs, etc.)

## Phase 3 — Ethernet & Wall Ports (Future)
- [ ] Plan ethernet runs — map which rooms get ports
- [ ] Decide on cable standard (Cat6 recommended)
- [ ] Purchase cable, keystone jacks, wall plates, patch panel
- [ ] Run cables (walls, attic, or basement)
- [ ] Terminate and test each run
- [ ] Install wall plates

## Equipment

### Ubiquiti UCG Ultra (Cloud Gateway Ultra)
- **Role:** Router/gateway/controller
- **Price:** $129
- **Ports:** (4) 1 GbE LAN RJ45 + (1) 2.5 GbE WAN RJ45
- **IDS/IPS throughput:** 1 Gbps
- **Max managed UniFi devices:** 30+
- **Max simultaneous clients:** 300+
- **CPU:** Quad-core ARM Cortex-A53 @ 1.5 GHz
- **RAM / Storage:** 3 GB / 16 GB
- **Power:** USB-C 5V/3A (adapter included), 6.2W max
- **Display:** 0.96" status display
- **VPN:** WireGuard, OpenVPN, IPsec, L2TP, Teleport, Site Magic
- **Notable:** Zone-based firewall, OSPF, multi-WAN load balancing, ad blocking, VLAN support
- **⚠️ Note:** Built-in switch (4x LAN ports) seems flaky — investigate after move
- [Tech Specs](https://techspecs.ui.com/unifi/cloud-gateways/ucg-ultra) | [Install Guide](https://dl.ui.com/qig/ucg-ultra)

### Ubiquiti U6 Pro (Access Point)
- **Role:** WiFi access point
- **Price:** $159
- **WiFi standard:** WiFi 6 (802.11ax)
- **Spatial streams:** 6 (4x4 on 5 GHz, 2x2 on 2.4 GHz)
- **Max data rate:** 5 GHz: 4.8 Gbps (BW160) / 2.4 GHz: 573.5 Mbps
- **Coverage:** ~1,500 ft²
- **Max clients:** 250+
- **Uplink:** (1) GbE RJ45
- **Power:** PoE (44–57V DC), 13W max
- **Mounting:** Ceiling or wall (mount included)
- **Weatherproofing:** IP54
- **Notable:** Fast roaming (802.11r/k/v), band steering, PPSK, guest isolation
- [Tech Specs](https://techspecs.ui.com/unifi/wifi/u6-pro) | [Install Guide](https://dl.ui.com/qig/u6-pro)

### Cable Modem
| Item | Model | Notes |
|------|-------|-------|
| Cable modem | TBD | Cable company installing 6/27 |
| Cable standard | Cat6 | Planned for future ethernet runs |

## Switch Candidates (Post-Move Purchase)

The UCG Ultra only has 4x LAN ports, so any real ethernet deployment will need an external switch. All of these integrate natively with UniFi Network/UCG Ultra.

| Model | Ports | Layer | PoE | Price | Best For |
|-------|-------|-------|-----|-------|----------|
| USW-Lite-16-PoE | 16 (8 PoE) | L2 | PoE+ (45W) | $199 | Wall-mountable, quiet, solid home choice |
| USW-24-PoE | 24 (16 PoE) | L2 | PoE+ (95W) | $379 | More ports, still fanless |
| USW-Pro-Max-24 | 24 | L3 | No | $449 | 2.5 GbE, future-proof, Etherlighting |
| USW-Pro-Max-24-PoE | 24 (all PoE++) | L3 | PoE++ (400W) | $799 | If adding cameras or many PoE APs |

**Likely best fit:** USW-Lite-16-PoE or USW-24-PoE — both are fanless (quiet), integrate with your UCG Ultra, and have enough ports for a house-wide ethernet run. Decide based on how many drops you end up running. The U6 Pro also needs PoE, so a PoE switch is the right call either way.

## Post-Move: Investigate UCG Ultra Switch
- Built-in switch on the UCG Ultra is behaving flaky — cause unknown
- May need external switch (Ubiquiti US-series or similar) depending on findings
- Revisit after move is complete

## Notes
- Think about where you want the "network closet" / patch panel to live before running cable
- Full UniFi ecosystem (UCG Ultra + U6 Pro) — future ethernet ports should work natively with UniFi network setup
