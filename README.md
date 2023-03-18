# notthebee/infra

An Ansible playbook that sets up an Ubuntu-based server with reasonable security, auto-updates, e-mail notifications for S.M.A.R.T. and Snapraid errors. Currently being completely rewritten

It assumes a fresh Ubuntu Server 20.04 install, access to a non-root user with sudo privileges and a public SSH key. This can be configured during the installation process.

The playbook is mostly being developed for personal use, so stuff is going to be constantly changing and breaking. Use at your own risk and don't expect any help in setting it up on your machine.

## Special thanks
* David Stephens for his [Ansible NAS](https://github.com/davestephens/ansible-nas) project. This is where I got the idea and "borrowed" a lot of concepts and implementations from.
* Jeff Geerling for his book, [Ansible for DevOps](https://www.ansiblefordevops.com/) and his [Ansible 101 series](https://www.youtube.com/watch?v=goclfp6a2IQ&list=PL2_OBreMn7FqZkvMYt6ATmgC0KAGGJNAN) on YouTube.
* Jonathan Hanson for his [SSH port juggling](https://gist.github.com/triplepoint/1ad6c6060c0f12112403d98180bcf0b4) implementation.
* Alex Kretzschmar and Chris Fisher from [Self Hosted Show](https://selfhosted.show/) for introducing me to the idea of Infrastracture as Code
* TylerAlterio for the [mergerfs](https://github.com/tyalt1/mediaserver/tree/master/roles/mergerfs) role
* Jake Howard and Alex Kretzschmar for the [snapraid](https://github.com/RealOrangeOne/ansible-role-snapraid/commits?author=IronicBadger) role

## Services included:
* [Home Assistant](https://hub.docker.com/r/homeassistant/home-assistant) 
* [Phoscon-GW](https://hub.docker.com/r/marthoc/deconz) 
* [nginx-proxy-manager](https://nginxproxymanager.com/) 




# Instructions

## Set up vault
ansible-vault create secret.yml
ansible-vault edit secret.yml
password:esteesmipass
:wq


## Install the dependencies:

ansible-galaxy install -r requirements.yml



# Set up ssh
ssh-keygen -o -a 100 -t ed25519 -f ~/.ssh/homeserver -C ismaelcv@gmail.com
ssh-copy-id -i ~/.ssh/homeserver ismael@192.168.1.77 

Set up vault
ansible-vault create secret.yml
ansible-vault edit secret.yml
password:esteesmipass
:wq

# Run ansible
ansible-playbook --ask-vault-pass run.yml


# Login to server via ssh
ssh ismael@192.168.1.77  
ssh -i ~/.ssh/homeserver ismael@192.168.1.77


 ansible all -m ping 



Questions
Whats the difference between roles and tasks?



Useful commands for microk8s

` Check the status of microk8s
sudo microk8s status 

Check nodes available
`sudo microk8s kubectl get nodes 