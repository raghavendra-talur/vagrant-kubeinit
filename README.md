# vagrant-kubeinit
A vagrant based kubeinit OKD setup

[Kubeinit](https://github.com/Kubeinit/kubeinit) is 
* ansible based
* production-like but developer focussed
* Kubernetes distribution installer
* for Libvirt hypervisors
* which is not minimal like Minikube, CodeReady etc.

## Use Case
I use this repo to iterate faster with my OKD development setups. Kubeinit
performs most of the work but I needed a wrapper to set up the libvirt
hypervisor and to store my configuration data.

## Requirements for the Vagrant VM
* 300GiB+ of disk space 
* 92GiB+ of memory
* 16 cpu cores

With the above listed resources, I have been able to get the setup up and
running consistently. More experiments to be done to determine the absolute
minimum resource requirement. The goal is to have something which is feasible on
a powerful laptop.

## How to run

```
export kubeinit_okd_openshift_deploy=True
export kubeinit_okd_openshift_registry_token_cloud_openshift_com="YOUR_REGISTRY_CLOUD_OPENSHIFT_COM_TOKEN"
export kubeinit_okd_openshift_registry_token_quay_io="YOUR_REGISTRY_QUAY_TOKEN"
export kubeinit_okd_openshift_registry_token_registry_connect_redhat_com="YOUR_REGISTRY_CONNECT_REDHAT_COM_TOKEN"
export kubeinit_okd_openshift_registry_token_registry_redhat_io="YOUR_REGISTRY_REDHAT_IO_TOKEN"
export kubeinit_okd_openshift_registry_token_email="YOUR_REGISTRY_EMAIL_ID"
vagrant up
```
Refer to Kubeinit documentation for more information on how to obtain those tokens.

The [gitignore](./.gitignore) file has an entry for `install.sh`. You can add
the above lines to the file to make a wrapper script.
