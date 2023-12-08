# Discourse Orchestration (Ansible)

![lint](https://github.com/alanbchristie/discourse-ansible/workflows/lint/badge.svg)

![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/alanbchristie/discourse-ansible)

A Playbook and Role to deploy [Discourse].

This project contains one Ansible role:-

*   **discourse**

You can find the common user-defined variables
in the role's `defaults/main.yaml` and less common variables in
`vars/main.yaml`.

## Prerequisites
You will need: -

-   [Poetry]
-   A kubernetes cluster with persistent storage
    with at least 2 cores and about 4Gi of RAM
-   An nginx ingres controller, a load-balancer and a
    hostname that resolves to your cluster
-   A certificate manager

## Configuration
You will need to provide some essential information prior to deployment.
Review the variables in `roles/discourse/defaults/main.yaml` and consider
providing values for all those that have `SetMe`. Not all of them are needed,
but you should review all variables prior to running the playbook.

---

[discourse]: https://www.discourse.org
[poetry]: https://python-poetry.org
