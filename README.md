# Installing MicroShift via Ansible

A playbook that deploys a MicroShift environment on a RHEL system.

## What is MicroShift?

As described https://github.com/redhat-et/microshift, MicroShift is a research project that is exploring how OpenShift<sup>1</sup> Kubernetes can be optimized for small form factor and edge computing.

Edge devices deployed out in the field pose very different operational, environmental, and business challenges from those of cloud computing. These motivate different engineering trade-offs for Kubernetes at the far edge than for cloud or near-edge scenarios. MicroShift's design goals cater to this:

- make frugal use of system resources (CPU, memory, network, storage, etc.),
- tolerate severe networking constraints,
- update (resp. rollback) securely, safely, speedily, and seamlessly (without disrupting workloads), and
- build on and integrate cleanly with edge-optimized OSes like Fedora IoT and RHEL for Edge, while
- providing a consistent development and management experience with standard OpenShift.

## How to Run the Ansible Playbook on RHEL

1. Install Ansible on your RHEL system

```
# dnf install -y ansible
```

2. Copy the inventory/hosts.sample file to inventory/hosts and fill out the appropriate variables

```
cp inventory/hosts.sample inventory/hosts
```

3. Install the required Ansible Collections

```
ansible-galaxy collection install -r requirements.yml
```

4. Run the Ansible Playbook on the RHEL system

```
ansible-playbook -i inventory/hosts playbook.yml
```

