# install jenkins 
 refer to jenkins installtion docuement

# create machine 
setup new ubuntu machine 

ssh into tthis new machine 
install open jdk with below commadn 
$ apt-get update 
$ apt install openjdk-7-jdk 

# add slave  
Go to Manage jenkins -> manage nodes

from left side menu ,select new node. give name and selcet option for permananent node ,click on ok 

# Node configuration
please fill below fields 

remote root directory as /home/ubuntu/jenkins

launch method -> launch slave agents via ssh 
host -> your slave machine ip
credentials -> add new jenkins credentials, it will poup for new credentials 
in jenkinss credential popup, select kind as ssh username with private key
Username - ubuntu
private key - enter directly , paste your pem file here 
Id- slave ssh
click on add

then save node configuration

now on left side menu select status and then click on launch. this will launch your slave. your slave is ready to use now

now create simple job in jenkins as freestyle project 

add build execution as echo hello and click build now
go to job console and check logs 

"Building remotely on slave1 (test) in workspace /home/ubuntu/jenkins/workspace/jobname"

this means our job is now executed on slave machine.




