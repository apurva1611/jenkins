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

ssh -A instance-user@instance-Id

service nginx status
sudo systemctl status jenkins
sudo systemctl restart nginx
sudo certbot --nginx -d jenkins.achirashah.com

https://jenkins.achirashah.com


## Assignment2 - Boran Yildirim
AIM: The goal of the assignment was to verify that Jenkins instance is accessible over jenkins.borancloud.me

ssh -A instance-user@instance-Id

service nginx status
sudo systemctl status jenkins
sudo systemctl restart nginx
sudo certbot --nginx -d jenkins.borancloud.me

https://jenkins.borancloud.me