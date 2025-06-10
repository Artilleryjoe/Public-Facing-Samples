
---

# Firmware Scan Report: Supply Chain Pre-Audit

## Scope
- Vendor: MicroCore Tech
- Product: Industrial 5G Router, Model R500
- Firmware: R500_firmware_v3.1.8.bin

---

## Critical Findings
    ```text
    [✓] Firmware hash match: CVE-2023-5113 backdoor
    [✗] Unexpected debug port open (31337)
    [✗] Root credentials found: user=root, pass=admin123

## Hash Check
    ```bash
    # SHA256 Hash Comparison
    $ sha256sum R500_firmware_v3.1.8.bin
    > b2c1f30a7a188db74f4e1471af... ← Match confirmed in CVE database

## remediation Workflow
    ```markdown
    1. Quarantine affected routers
    2. Notify vendor and request clean firmware build
    3. Audit firmware supply chain for future devices

## Lessons Learned
Always request an SBOM (Software Bill of Materials) from hardware and firmware suppliers.

Recommendation:
Integrate static firmware scans using binwalk and firmwalker into CI pipelines.

