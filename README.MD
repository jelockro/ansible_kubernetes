The following setup is necessary for the vscode remote workflow that I've setup
the ansible configuration file exists @ /etc/ansible/ansible.cfg due to the fact
that the workspace that the ansible project resides in is an nfs share, and as such
its permissions are too open for ansible to allow an ansible.cfg to work within this directory
...this is a todo for later, if I can selectively restrict certain folders within the workspace 
or something else.

also, in order for ansible-vault to vs-code plugin to work, there must be no setting of default variables
for vault-keypass in the ansible.cfg.  

The settings will then reside only in the vscode configuration...however, the pem file must be consistent
for vault secrets to be unencrypted.  

Also, since I use a python virtualenvironment, the python interpreter must be set through the python vs-code 
module and the full path to the ansible-vault binary must be provided to the ansible-vault module configuration.

provisioner/ansible host machine/ must have sshpass installed:
sudo apt-get install -y ssh-pass