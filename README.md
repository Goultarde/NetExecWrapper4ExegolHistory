# 🛠️ nxcwrap.py – NetExec Wrapper for Exegol-History

## Description

`nxcwrap.py` is a wrapper for [NetExec (`nxc`)](https://github.com/NetExec-net/nxc) designed to be used **inside an Exegol container**.  
It enhances your workflow by automatically syncing discovered credentials and hosts from NetExec into [Exegol-History](https://github.com/ThePorgs/Exegol-history).

After executing any `nxc` command, it will:

- Add discovered or used **credentials** (plaintext or hashes) to Exegol-History
- Add **host IPs and hostnames** to Exegol-History

---

## Installation (inside Exegol)

```bash
bash <(curl -sSL https://raw.githubusercontent.com/Frozenka/nxcwrap/refs/heads/main/install_nxcwraper.sh)

```
## Installation my-ressources :
```bash
echo 'bash <(curl -sSL https://raw.githubusercontent.com/Frozenka/nxcwrap/refs/heads/main/install_nxcwraper.sh)' > ~/.exegol/my-resources/setup/load_user_setup.sh
```

## Usage

Run `nxc` as usual:

```bash
nxc smb 10.10.10.10 -u admin -p password123
```

This wrapper will:

1. Run the actual NetExec command
2. Parse the local `smb.db` workspace
3. Auto-push new credentials and hosts into Exegol-History (if not already known)

---
 
 
## Features

- ✅ Transparent execution of `nxc`
- ✅ Automatic credential and host sync with Exegol-History
- ✅ NTLM hash parsing support

---

## Requirements

- Exegol container with:
  - NetExec installed in `/opt/tools/NetExec/`
  - Exegol-History installed in `/opt/tools/Exegol-history/`
- Python dependency: `colorama`

---

## Limitations

- Only works inside Exegol  

---

 
