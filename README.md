# Frouros agent: published installer hash

This repository is the independent reference for the Frouros (NVX) agent installer served by
`https://nvx.netcy.com/frouros/install.sh`. It is maintained by NOVATEX/Netcy and updated with every release.

## Verified install

Runs the installer only if its hash matches this file:

```
curl -fsSL --proto '=https' https://nvx.netcy.com/frouros/install.sh -o frouros-install.sh &&
curl -fsSL --proto '=https' 'https://raw.githubusercontent.com/novatex-solutions/frouros-release/main/install.sh.sha256' -o frouros-install.sh.sha256 &&
sha256sum -c --strict frouros-install.sh.sha256 &&
sudo bash frouros-install.sh <YOUR-ACTIVATION-CODE>
```

The installer itself verifies the agent package against a checksum embedded in the script, so a matching
installer hash also covers the agent code. If the check fails, nothing is installed. Contact Netcy support
before retrying.
