# -*- mode: ruby -*-
# vi: set ft=ruby :
#
DISKSIZE = "300G"
MEMORY = "93804"
CPUS = "16"
kubeinit_okd_openshift_registry_token_cloud_openshift_com = ENV['kubeinit_okd_openshift_registry_token_cloud_openshift_com'] || ""
kubeinit_okd_openshift_registry_token_quay_io = ENV['kubeinit_okd_openshift_registry_token_quay_io'] || ""
kubeinit_okd_openshift_registry_token_registry_connect_redhat_com = ENV['kubeinit_okd_openshift_registry_token_registry_connect_redhat_com'] || ""
kubeinit_okd_openshift_registry_token_registry_redhat_io = ENV['kubeinit_okd_openshift_registry_token_registry_redhat_io'] || ""
kubeinit_okd_openshift_registry_token_email = ENV['kubeinit_okd_openshift_registry_token_email'] || ""
kubeinit_okd_openshift_deploy_true = ENV[''] || "TRUE"

Vagrant.configure("2") do |config|
  config.vm.box = "fedora/34-cloud-base"
  config.vm.provider :libvirt do |lv|
    lv.memory = MEMORY
    lv.cpus = CPUS
    lv.storage :file, :size => DISKSIZE
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.extra_vars = {
      kubeinit_okd_openshift_registry_token_cloud_openshift_com: kubeinit_okd_openshift_registry_token_cloud_openshift_com,
      kubeinit_okd_openshift_registry_token_quay_io: kubeinit_okd_openshift_registry_token_quay_io,
      kubeinit_okd_openshift_registry_token_registry_connect_redhat_com: kubeinit_okd_openshift_registry_token_registry_connect_redhat_com,
      kubeinit_okd_openshift_registry_token_registry_redhat_io: kubeinit_okd_openshift_registry_token_registry_redhat_io,
      kubeinit_okd_openshift_registry_token_email: kubeinit_okd_openshift_registry_token_email,
      kubeinit_okd_openshift_deploy_true: kubeinit_okd_openshift_deploy_true
    }
  end
end
