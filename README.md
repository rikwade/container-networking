#A VM for Docker and K8s lab exercises

$ vagrant up

will pull the Ubuntu bento/18.10 VM image, a minimal Ubuntu image, and then run
the Ansible provisioner using playbook.yml.

The Ansible playbook updates packages, installs Docker and the Ubuntu Snap for MicroK8s, minikube Kubernetes. 

The VM mounts a host filesystem directory called "sync" which is used to share
lab exercise files with the VM, such as documentation and configuration files.

Richard Wade
ricwade@cisco.com
February 2019
