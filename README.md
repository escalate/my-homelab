[![Test](https://github.com/escalate/my-homelab/actions/workflows/test.yml/badge.svg?branch=master&event=push)](https://github.com/escalate/my-homelab/actions/workflows/test.yml)

# My Homelab

The central repository for managing my Raspberry Pi Homelab, based on an Ansible GitOps workflow.

## Setup

### Create custom Raspberry Pi OS disk image

Tool: https://github.com/escalate/ansible-gitops-raspberry-pi-os-custom-disk-image

#### pi3.fritz.box

```
export ANSIBLE_HOSTNAME="pi3.fritz.box"
export ANSIBLE_HOSTGROUP="pi3"
export ANSIBLE_REPOSITORY_URL="https://github.com/escalate/my-homelab.git"
export ANSIBLE_VAULT_PASSWORD="$(cat ../my-homelab/.vault_pass.txt)"
make build-64bit
```

#### pi4.fritz.box

```
export ANSIBLE_HOSTNAME="pi4.fritz.box"
export ANSIBLE_HOSTGROUP="pi4"
export ANSIBLE_REPOSITORY_URL="https://github.com/escalate/my-homelab.git"
export ANSIBLE_VAULT_PASSWORD="$(cat ../my-homelab/.vault_pass.txt)"
make build-64bit
```

### Flash custom Raspberry Pi OS disk image on SD Card

- Open [balenaEtcher](https://etcher.balena.io/) tool
- Click `Flash from file` button
- Select `output.img`
- Select SD Card as target
- Click `Flash!"` button

### Connect to device

- Insert SD card into Raspberry Pi
- Start device
- Log in with the standard user `pi` and the password `raspberry`

#### pi3.fritz.box

```
ssh pi3.local
```

#### pi4.fritz.box

```
ssh pi4.local
```

## License

MIT
