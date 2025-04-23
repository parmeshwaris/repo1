#!/bin/bash
# install Jenkins, Java, etc. first...

# Set Jenkins URL
echo "<?xml version='1.1' encoding='UTF-8'?>
<jenkins.model.JenkinsLocationConfiguration>
  <jenkinsUrl>http://$(curl -s http://checkip.amazonaws.com):8080/</jenkinsUrl>
</jenkins.model.JenkinsLocationConfiguration>" > /var/lib/jenkins/jenkins.model.JenkinsLocationConfiguration.xml

# Restart Jenkins to apply the change
systemctl restart jenkins
