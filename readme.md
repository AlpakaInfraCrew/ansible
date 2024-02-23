# AIC Ansible
## Installation of Dev Environment
1. Installation of ansible
  - Option 1: Creating venv, and installing with pip install -r requirements.txt
2. `ansible-galaxy install -r requirements.yml --force-with-deps --force`
3. Creating `password_file` with ansible-secret password

## Structure
- `roles` contains custom roles
- `roles_galaxy` contains roles automatically installed by `ansible-galaxy`

## Add Keys
1. edit `roles/user/vars/all_users.yml`
2. add to `userconfig.yml`
3. Create a PR
4. Add someone who already is in `userconfig.yml` to the reviewers.
5. Wait until someone rolls out your user
6. ...
7. Profit!