# jenkins_SSH_AWSDeployment

open jenkins.... $ cd .ssh/
vi id-rsa.pub
copy the content.....

open remote server
cd .ssh/
echo ...content.... >> authorized_keys

Check using jenkin server.... ssh username@remotehost

change permission for webserver : sudo chmod -R 777 /var/www/html/

run this command....
rsync -avz -e "ssh -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null" --progress /var/lib/jenkins/workspace/test/* ubuntu@ec2-52-207-244-134.compute-1.amazonaws.com:/var/www/html/
-----jenkin build file : /var/lib/jenkins/workspace/test/*
----new webserver location ubuntu@ec2-52-207-244-134.compute-1.amazonaws.com:/var/www/html/

