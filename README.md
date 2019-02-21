#A VM for Docker and K8s lab exercises

$ vagrant up

will pull the Ubuntu bento/18.10 VM image, a minimal Ubuntu image, and then run
the Ansible provisioner using playbook.yml.

The Ansible playbook updates packages, installs Docker and the Ubuntu Snap for
MicroK8s, minikube Kubernetes. It also installs Nginx to act as a local Web
server on the VM for access to lab exercise documentation.

The VM mounts a host filesystem directory called "sync" which is used to share
lab exercise files with the VM, such as documentation and configuration files.

ricwade
February 2019
