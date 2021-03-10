# Discourse Orchestration (Ansible)

![lint](https://github.com/InformaticsMatters/discourse-ansible/workflows/lint/badge.svg)

![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/informaticsmatters/discourse-ansible)

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

## Prerequisites
You will need: -

-   A kubernetes cluster with persistent storage
-   An ingres controller (like ngnix), a load-balancer and a
    hostname that resolves to your cluster
-   At least one available core, ideally 2 or 3
-   A certificate manager
-   A named PodSecurityPolicy with admin capabilities

## Configuration
You will need to provide some essential information prior to deployment.
Review the variables in `roles/discourse/defaults/main.yaml` and consider
providing values for all those that have `setMe`. Not all of them are needed,
but you should review all variables prior to running the playbook.

---

[awx]: https://github.com/ansible/awx
[discourse]: https://www.discourse.org
[infrastructure]: https://github.com/InformaticsMatters/ansible-infrastructure
