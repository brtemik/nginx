# Deploying Nginx as a proxy with Ansible
## Task
Write an Ansible playbook that will:
* install selected version of Nginx package; 
* configure it to work as a proxy;
* use parameter to state listening port.

## Solution
The playbook is *nginx.yml*.

It: 
1) installs selected nginx package; 
2) starts the service;
3) adds proxy settings to conf file;
4) restarts service.

The playbook was run with command:

```ansible-playbook -i localhost nginx.yml --extra-vars "version=latest src=80 dst=3000"```

It was tested on a [GCP VM Ubuntu 20](http://34.90.39.66).
So if you click on the link (external IP of a VM) you will access to port *80* but redirected to port *3000* with Grafana (Only ports 80 and 433 are open). 
