## Hosts (Install with Vagrant):
```
192.168.1.100 Ubuntu 18.04 with installed Ansible
192.168.1.101 Centos 7
192.168.1.102 Ubuntu 18.04
```			
## Install Ansible
```
$ sudo apt-add-repository --yes --update ppa:ansible/ansible
$ sudo apt install python3-pip
$ sudo apt install ansible
```		
## Keys for connection without password
```
192.168.1.100
ssh-keygen
/home/vagrant/key_centos_ubuntu
/home/vagrant/key_centos_ubuntuюзги
add keys to authorized_keys file 192.168.1.101 and 192.168.1.102
```		
## Disable PasswordAuthentication
```
sudo nano /etc/ssh/sshd_config
PasswordAuthentication no
```
## Inventory file
```
[local]
centos7          ansible_host=192.168.1.101 ansible_user=max   		ansible_ssh_private_key_file=/home/vagrant/.ssh/key_centos_ubuntu
ubuntu1804       ansible_host=192.168.1.102 ansible_user=vagrant  	ansible_ssh_private_key_file=/home/vagrant/.ssh/key_centos_ubuntu
```
## Connect to the hosts
```
sudo ansible -m ping -i hosts all
centos7 | SUCCESS => {
	"ansible_facts": {
		"discovered_interpreter_python": "/usr/bin/python"
	},
	"changed": false,
	"ping": "pong"
}
ubuntu1804 | SUCCESS => {
	"ansible_facts": {
		"discovered_interpreter_python": "/usr/bin/python"
	},
	"changed": false,
	"ping": "pong"
}
```
## Print out host names and IP
```
sudo ansible -m shell -a "hostname -I" -i hosts all

ubuntu1804 | CHANGED | rc=0 >>
10.0.2.15 192.168.1.102

centos7 | CHANGED | rc=0 >>
10.0.2.15 192.168.1.101
```		
## Upgrade packages
```		
sudo ansible -m shell -a 'apt update' -b -i hosts ubuntu1804
210 packages can be upgraded. Run 'apt list --upgradable' to see them.

sudo ansible -m shell -a 'yum -y update' -b -i hosts centos7
No packages marked for update
```		
## Create new user
```
sudo ansible -m shell -a 'useradd ansible_user' -b -i hosts all
```		
## Apply sudo rules for its
```
sudo ansible -m shell -a 'usermod -aG sudo ansible_user' -b -i hosts all
```



## `Links to repositories`

![alt-текст](https://i.ibb.co/72VSyLr/Git-Hub-90.png "GitHub") **[GitHub](https://github.com/trenonby)**

**https://github.com/trenonby**

![alt-текст](https://i.ibb.co/LRN1f6x/Git-Lab-90.png "GitLab") **[GitLab](https://gitlab.com/trenonby)**

**https://gitlab.com/trenonby**

![alt-текст](https://i.ibb.co/72S6h9F/Bitbucket-90.jpg "Bitbucket") **[Bitbucket](https://bitbucket.org/trenonby)**

**https://bitbucket.org/trenonby/**s

## `Slack channel`

![alt-текст](https://i.ibb.co/PDFBKWT/Slack-90.png "Slack") **[Slack](https://sa-itacademy-by.slack.com/messages/CKVFH9VS6/apps/A676ADMV5/)**

**integration_events_MK**  
**https://sa-itacademy-by.slack.com/messages/CKVFH9VS6/apps/A676ADMV5/**
