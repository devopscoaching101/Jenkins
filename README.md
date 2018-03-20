# Jenkins prerequisite
Recommended hardware configuration for a small team:

1 GB+ of RAM

50 GB+ of drive space


# installation on ubuntu

ssh /putty into your cloud VM. 

once you logged in to VM ,then change user to root with below commanf

$ sudo su

then execute below commands 

$ wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
$  sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
$  apt-get update
$  apt-get install jenkins

# check if jenkins is running
by default, jenkins will run on port 8080 ,we will check if that port is being used by jenkins
$ netstat -tunlp |grep 8080

if you get putput for above command,it means jenkins is installed correctly and running

# security group

Make sure you have allowed 8080 port in your security group ( in inbound rules )

# run in browser

now go to your browser and access jenkins using public ip of your machine

http://publicIP:8080

# unlocking jenkins
You will see ,you will be asked to enter admin password, to get admin password you need to execute below 

$ sudo cat /var/jenkins_home/secrets/initialAdminPassword

copy and paste output of above. 

# plugins installation 
After unlocking Jenkins, the Customize Jenkins page appears. Here you can install any number of useful plugins as part of your initial setup.


Click one of the two options shown:

Install suggested plugins - to install the recommended set of plugins, which are based on most common use cases.

Select plugins to install - to choose which set of plugins to initially install. When you first access the plugin selection page, the suggested plugins are selected by default.

The setup wizard shows the progression of Jenkins being configured and your chosen set of Jenkins plugins being installed. This process may take a few minutes.


# Creating the first administrator user
Finally, after customizing Jenkins with plugins, Jenkins asks you to create your first administrator user.

When the Create First Admin User page appears, specify the details for your administrator user in the respective fields and click Save and Finish.

When the Jenkins is ready page appears, click Start using Jenkins.
