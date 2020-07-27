# Discourse Orchestration (Ansible)

[![Build Status](https://travis-ci.com/InformaticsMatters/discourse-ansible.svg?branch=master)](https://travis-ci.com/InformaticsMatters/discourse-ansible)

A playbook and Role to deploy [Discourse], suitable for execution by
[AWX].

This project contains one Ansible role:-

*   **discourse**

>   Note: The Role is designed to be executed from within our AWX server
    where credentials for the cluster (Kubernetes) reside. If you're not
    running from AWX (discouraged) then you will need to provide
    values for the variables that would be injected by AWX.

We depend on our [infrastructure] project's Kubernetes
**Certificate Manager** to generate https certificates.

As with all of our playbooks you can find the common user-defined variables
in the role's `defaults/main.yaml` and less common variables in
`vars/main.yaml`.

## Ansible Vault
The project uses files encrypted by Ansible Vault. AWX will inject
the vault secret but if you want to edit or inspect the secret file
(`roles/website/vars/pull-secrets.vault`) you will need
the vault key, which can be found in our **KeePass** application under
`website-ansible -> Ansible Vault Password`: -

    $ ansible-vault edit roles/website/vars/pull-secrets.vault

---

[awx]: https://github.com/ansible/awx
[discourse]: https://www.discourse.org
[infrastructure]: https://github.com/InformaticsMatters/ansible-infrastructure
