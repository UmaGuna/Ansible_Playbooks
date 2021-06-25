 
## package module can identify the os family and appropriate modules for the same software name for all the os

## for ubuntu os
sudo apt-get install git -y 
sudo apt-get install apache2 -y
 
# for RedHat/CentOS  
sudo yum install git -y
sudo yum install https -y 


In both the above cases , for installable software < Git >  is same for both os , 
so we can optimize the play using __package__
but it will not possible for the apache software 


---
- hosts: all
  become: yes
  tasks:
  package:
    name: git
    state: present
-----

Different software name , we can use __Ansible variable__

** create Groups and ansible variable in inventory file like

----
[ubuntu]
172.31.26.196

[redhat]
172.31.25.93

[webservers]
172.31.26.196 package_name = 'apache2'
172.31.25.93  package_name = 'httpd'



------

## Now Replace apt and yum with package module and also replace all in hosts with webservers


tekton - server less
helmchat  - kubernities 

ARGO CD 



