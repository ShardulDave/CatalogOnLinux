# CatalogOnLinux

## Login Information for grader

ssh grader@34.218.246.194 -p 2200 -i grader_key<br>
url: http://34.218.246.194.xip.io/

## Firewall
1) Created Amazon Lightsail instance
2) ssh into the machine
3) change the default ssh port to 2200 
    1) sudo nano /etc/ssh/sshd_config
    2) sudo service sshd restart and add the ports
4) Enabled the ports udp port 123 and tcp port 2200 on aws gui. Also disable port 22 on it.
5) Enabled firewall
```bash
sudo ufw status
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow www
sudo ufw allow 123/udp
sudo ufw allow 2200/tcp
sudo ufw enable 
```

2200/tcp                   ALLOW       Anywhere                  
123/udp                    ALLOW       Anywhere                  
80/tcp                     ALLOW       Anywhere                  
2200/tcp (v6)              ALLOW       Anywhere (v6)             
123/udp (v6)               ALLOW       Anywhere (v6)             
80/tcp (v6)                ALLOW       Anywhere (v6)   

## default time-zone is UTC

```bash
timedatectl
```

## Add user name grader

1) create key using ssh-keygen on local machine
2) https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/managing-users.html


## Giving sudo to grader

1) sudo nano /etc/sudoers.d/grader
Type: grader ALL=(ALL) NOPASSWD:ALL

## Software installed

```bash
sudo apt-get install apache2
sudo apt-get install python-setuptools libapache2-mod-wsgi
sudo apt-get install postgresql
sudo apt-get install git
sudo apt-get install python-pip
sudo pip install -r requirements.txt
sudo apt-get -qqy install postgresql python-psycopg2
sudo apt-get update
sudo apt-get upgrade
```
## References
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-16-04
https://github.com/jungleBadger/-nanodegree-linux-server


