# Wildfly9 cluster

Lab include:
- Wildfly9
  Master: 33.33.33.31
  Node1: 33.33.33.31
  Node2: 33.33.33.32

- Preinstaled
  curl
  JDK 8u151
  JRE 8u151

- Playbook for Jenkins

Menagment Console working:
  Port: 9990 on host machine
  User: Admin
  Password: passw0rd!

App is serving on :8080.

# Just type

    vagrant up

# Also, 

I use vagrant-vbguest, with autosync turn on
That's only vagran in project.

Still work in progress. 


# Tech stack

- Vagrant
- Ansible
- Jenkins
- Debian
- Wildfly