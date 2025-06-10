# Incident Report: Rogue Drone RF Jamming Attempt

## Summary
Aerial RF interference was detected above Facility 4. The source was confirmed to be a **rogue drone** emitting targeted jamming frequencies that disrupted network operations.

> **Note:** This incident demonstrates increasing sophistication in low-cost aerial surveillance and interference tactics.

---

## Technical Analysis

### Observed Frequency Bands
    ```text
    - 2.420 GHz – 2.480 GHz (Wi-Fi)
    - 1.563 GHz (GPS L1 band)

## Indicators of Compromise (IoCs)
- Repeating RF bursts approximately 250ms apart

- Unregistered drone ID (OpenDroneID failure)

- Nearby mesh node logs: Packet loss spike from 2% to 43%

## Mitigation actions
   # Step 1: Isolate affected access points
    $ sudo netctl disable wlan-node-6
    
    # Step 2: Trigger spectrum scan
    $ rfwatch --scan --duration 60s
    
    # Step 3: Notify authorities
    Contact: fcc.report@fcc.gov

    
## Outcome & Next Steps
| Action                       | Status    |
| ---------------------------- | --------- |
| Mesh isolation               | Completed |
| RF sweep                     | Logged    |
| Law enforcement notification | Pending   |
    ```Markdown
    Recommendation:
    Deploy real-time RF spectrum monitoring using HackRF One and GNU Radio.
