# ansible-roles

[![lint](https://github.com/mateusz-uminski/ansible-roles/actions/workflows/lint.yaml/badge.svg)](https://github.com/mateusz-uminski/ansible-roles/actions/workflows/lint.yaml)
[![tests](https://github.com/mateusz-uminski/ansible-roles/actions/workflows/tests.yaml/badge.svg)](https://github.com/mateusz-uminski/ansible-roles/actions/workflows/tests.yaml)

This repository serves as a collection of Ansible roles that I use for configuring test environments, learning and verifying unconventional ideas.

Besides the README.md further documentation can be found in commits, code comments and nested README files.

Feel free to explore and copy everything you want. Enjoy!


# Requirements
1. Python3


# Prerequisites
1. Configure environment:
```sh
cd $(git rev-parse --show-toplevel)
python3 -m venv venv/
source venv/bin/activate
pip install pip --upgrade
pip install -r requirements.txt
```


# Usage

## Execute molecule tests for a given role and platform
```sh
cd $(git rev-parse --show-toplevel)
make test platform=debian12-systemd role=docker
```

## Execute molecule tests for a given role on all platforms
```sh
cd $(git rev-parse --show-toplevel)
make tests role=docker
```
