# ansible-v2c

This is a set of Ansible scripts that migrates Java workloads from existing deployments in Tomcat and JBoss containers to new deployments on the OpenShift Container Platform.

To use, create an inventory file that has a set of application servers and a single build server. An example is below:

```
[appservers]
10.11.95.103 ansible_user=cloud-user ansible_become=true
10.11.95.106 ansible_user=cloud-user ansible_become=true
10.11.95.168 ansible_user=cloud-user ansible_become=true

[buildservers]
10.11.95.110 ansible_user=cloud-user ansible_become=true
```

Then, just run the playbooks like so:

```
$ ansible-playbook -i inventory site.yml
```

Make sure that the account you're using on the "build server" has logged into an OpenShift cluster and has a current token.

Here's a video of me running the playbooks:

https://youtu.be/Fl8Pnuk9JLo

