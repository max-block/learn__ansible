--> Install via pipx
pipx install ansible
pipx inject ansible passlib

--> Install galaxy role from file
ansible-galaxy install -r requirements.yml

--> Override installed galaxy role from file
ansible-galaxy install -r requirements.yml --force

--> Limit hosts
ansible-playbook ... --limit hostA,hostB,hostC

--> Limit hosts via range
ansible-playbook ... --limit $(echo node{7..11} | tr ' ' ',')

--> Exclude hosts
ansible-playbook ... --limit '!hostA,!hostB'


--> Connect via password
ansible playbook playbook.yml --ask-pass

It can be the error: " msg: to use the 'ssh' connection type with passwords, you must install the sshpass program"
On macOS: brew install hudochenkov/sshpass/sshpass
On linux: apt install sshpass

--> Don't print skipped tasks.
Add in ansible.cfg
[defaults]
display_skipped_hosts = False