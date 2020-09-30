## Assignment 2 - Boran Yildirim
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