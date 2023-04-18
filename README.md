# Sahl (سهل) 


Is an Ansible playbook for effortless (sahl) installation of your favorite developing tools with Ansible

It assumes a fresh Ubuntu Server 20.04 install, access to a non-root user with sudo privileges.

The playbook is mostly being developed for personal use, so stuff is going to be constantly changing and breaking. Use at your own risk and if you have any questions, feel free to contact me.

 
<br>

# Requirements - Assuming a fresh linux installation
------------
1) Ubuntu 20.04
2) Install Ansible 



To verify whether pip is already installed for your preferred Python:
```
python3 -m pip -V
```


If you see an error like No module named pip, you’ll need to install pip under your chosen Python interpreter before proceeding. This may mean installing an additional OS package (for example, python3-pip), or installing the latest pip directly from the Python Packaging Authority by running the following:

```
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py --user
```





```
sudo apt update
sudo apt install ansible
```


# Run ansible
```
ansible-playbook playbook.yml --ask-become
```


After Ansible has installed all the tools, you will need to do the following:

- `wsl --shutdown` in powershell to restart WSL with the new config
- restart VS code
- Check systemd is running with ` systemctl list-unit-files --type=service `
- Check microk8s is running with `sudo microk8s status`
- Set `Zsh` as default terminal in VS code :
    - In `VS terminal > select default profle > zsh`
- Install [MesloLGS](https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k) font in windows
-  Add MesloLGS font to  VS code: in  `Terminal>Integrated:` add  `MesloLGS NF` 



<br>

Requirements
------------
- Ubuntu Server 20.04
- Ansible >= 2.9
- Python >= 3.8
