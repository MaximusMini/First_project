## `Ansible.Run`

## `Docker.Landing`

**Dockerfile**

```
	FROM alpine:latest
	RUN apk add --update
	RUN echo "**** install Python ****"
	RUN apk add --no-cache python3
	RUN echo "**** Python version ****"
	RUN python3 --version
	RUN echo "**** COPY APP ****"
	COPY ./app_python /home/app_python
	RUN echo "**** set EXPOSE ****"
	EXPOSE 8000
	WORKDIR /home/app_python
	RUN echo "**** run Python ****"
	CMD python3 -m http.server --cgi
```

**APP PYTHON**

```
hello.py
--------

#!/usr/bin/python

print ("Content-type: text/html \n")
print("<h1>Hello World!</h1>")
```




**Unlock Jenkins**

## Inventory file - hosts.yaml

```
---
all_hosts:
 hosts:
  centos7:
   ansible_user: max
   ansible_host: 192.168.1.101
   ansible_ssh_private_key_file: /home/vagrant/.ssh/key_centos_ubuntu
  ubuntu:
   ansible_user: vagrant
   ansible_host: 192.168.1.102
   ansible_ssh_private_key_file: /home/vagrant/.ssh/key_centos_ubuntu
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
