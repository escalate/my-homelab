[![Test](https://github.com/escalate/my-homelab/actions/workflows/test.yml/badge.svg?branch=master&event=push)](https://github.com/escalate/my-homelab/actions/workflows/test.yml)

# My Homelab

## Create custom Raspberry Pi OS disk os

Tool: https://github.com/escalate/ansible-gitops-raspberry-pi-os-custom-disk-image

```
export ANSIBLE_HOSTNAME='homelab.fritz.box'
export ANSIBLE_REPOSITORY_URL='https://github.com/escalate/my-homelab.git'
export ANSIBLE_VAULT_PASSWORD='REDACTED'
make build-64bit
```

### Flash custom Raspberry Pi OS image on SD Card

- Open balenaEtcher tool
- Click "Flash from file" button
- Select YYYY-MM-DD-raspios-bookworm-arm64-lite.img
- Select SD Card as target
- Click "Flash!" button
- Close balenaEtcher tool
