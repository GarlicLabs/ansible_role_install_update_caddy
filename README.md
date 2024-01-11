# ansible_role_install_update_caddy

[![Validate infrastructure as code](https://github.com/garliclabs/ansible_role_install_update_caddy/actions/workflows/validation.yml/badge.svg)](https://github.com/garliclabs/ansible_role_install_update_caddy/actions/workflows/validation.yml)

Installs or updates a caddy on linux.  

Please note currently just debian is implemented!  

## Requirements

Debian, apt package manager

## Role Variables

**caddy_version:** Verion to be installed  
**caddy_installation_plattform:** Plattform used e.g. linux_amd64.deb  
**caddy_url:** Url to download caddy, if not set will be assembled  
**caddy_installed_version:** Existing version (will be overrided but needs to be initialized)  

## Development

### Testing

* Create venv: `python3 -m venv ./venv`
* Install pip requirements: `venv/bin/pip install -r pip_requirements.txt`
* Execute tests `venv/bin/molecule test`

### Linting & static security analyser

Both the linter and the static security analyser are running on each push on the github actions pipeline.  

* As linter [ansible-lint](https://ansible.readthedocs.io/projects/lint/) is used. For installation documentation see [ansible lint installing](https://ansible.readthedocs.io/projects/lint/)
  * Just run `ansible-lint`

* To check if there are any passwords, tokens... hardcoded, [kics](https://kics.io/index.html) is used to ensure a secure IaC repository.  
  * Run it locally `docker run -t -v $PWD:/path checkmarx/kics:latest scan -p /path -o "/path/"`

## License

GNU General Public License version 3
