# Test VM on Nixos 19.09

This is a basic shell and ansible provisioned vagrant vm

**1. Downloads:**
- virtualbox
- vagrant

**2. Clone project**

**3. Vagrant up**

**4. Additional:**

**additional needs**
vagrant plugin install vagrant-proxyconf

**adjust nixos host file (in this case), add following entry:**
192.168.33.111 tomcat-vm 

**configuration.nix add:**
environment.etc.hosts.mode = "0644";

**tomcat will reachable at:**
localhost:4000
