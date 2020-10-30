## Assignment2 - Apurva Mathur
AIM: The goal of the assignment was to run Jenkins on our subdomain(jenkins.apurvamathur.me). The jenkins is running on an EC2 instance.

Commands used are:
1. To ssh into ec2 instance use:
ssh -i KeyPairLatest.pem ubuntu@ec2-35-170-63-110.compute-1 amazonaws.com
ssh -i KeyPairLatest.pem ubuntu@(Public dns)

2. Command to restart nginx and see if cerbot is running or not:
sudo nginx -t
sudo systemctl restart nginx
sudo certbot --nginx -d jenkins.example.com

3. Jenkins will be accesssible on subdomain.(eg http://jenkins.apurvamathur.me)


## Assignment2 - Achira Shah
AIM: The goal of the assignment was to verify that Jenkins instance is accessible over jenkins.achirashah.com

ssh -i "mykeypair" instance-user@instance-Id

service nginx status
sudo systemctl status jenkins
sudo systemctl restart nginx
sudo certbot --nginx -d jenkins.achirashah.com

https://jenkins.achirashah.com


## Assignment2 - Boran Yildirim
AIM: The goal of the assignment was to verify that Jenkins instance is accessible over jenkins.borancloud.xyz

```
ssh -i "cloud-kp.pem" ubuntu@ec2-3-130-67-236.us-east-2.compute.amazonaws.com
```

```
service nginx status
sudo systemctl status jenkins
sudo systemctl restart nginx
sudo certbot --nginx -d jenkins.borancloud.xyz
```

https://jenkins.borancloud.xyz

## Assignment3 - Boran Yildirim

Setup network, EC2 and jenkins:
```
ansible-playbook site.yml --tags "create" -i hosts -e "@boran_common_conf.yml"

ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook site.yml --tags "boran-jenkins" -i hosts -e "@boran_jenkins_conf.yml"
```

After setup vpc, copy the vpc_id into boran_terminate_conf.yml.
To terminate the instance:
```
ansible-playbook site.yml --tags "delete" -e "@boran_terminate_conf.yml"
```

## Assignment3 - Achira Shah

Setup network, EC2 and jenkins:
$ ansible-playbook site.yml --tags "create" -i hosts -e "@achira_common_conf.yml"

$ ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook site.yml --tags "achira-jenkins" -i hosts -e "@achira_jenkins_conf.yml"

To terminate the instance:
$ ansible-playbook site.yml --tags "delete" -e "@achira_terminate_conf.yml"

## Assignment3 - Apurva Mathur

Setup network, EC2 and jenkins:
$ ansible-playbook site.yml --tags "create" -i hosts -e "@apurva_common_conf.yml"

$ ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook site.yml --tags "apurva-jenkins" -i hosts -e "@apurva_jenkins_conf.yml"

To terminate the instance:
$ ansible-playbook site.yml --tags "delete" -e "@apurva_terminate_conf.yml"

In case the host does not identify known_hosts i.e. ssh error comes do the foloowing: 
1. ssh-keygen -s f sshpath -R ip_of_ec2_instance
ex: ssh-keygen -s f "/home/apurva/.ssh/known_hosts" -R 107.20.242.17
2. ssh-keygen -R 107.20.242.17

ssh -i "~/.ssh/rootKeyPair" ubuntu@ec2-107-20-242-17.compute-1.amazonaws.com



