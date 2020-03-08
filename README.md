**Test VM on Nixos 19.09**

1. Downloads:
- virtualbox
- vagrant

2. Clone project
3. vagrant up

# additional needs
vagrant plugin install vagrant-proxyconf

# adjust nixos host file (in this case), add:
192.168.33.111  sts-project-vm

# configuration.nix add:
environment.etc.hosts.mode = "0644";

# tomcat will reachable at:
localhost:4000
