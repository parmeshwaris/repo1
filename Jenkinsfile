#!/bin/bash
# install Jenkins, Java, etc. first...




# Get the public IP of the current EC2 instance
CURRENT_IP=$(curl -s http://checkip.amazonaws.com)

# File to update — change this path as needed
CONFIG_FILE="/var/lib/jenkins/jenkins.model.JenkinsLocationConfiguration.xml"

# Backup the original
cp "$CONFIG_FILE" "$CONFIG_FILE.bak"

# Update the Jenkins URL inside the XML config file
cat > "$CONFIG_FILE" <<EOF
<?xml version='1.1' encoding='UTF-8'?>
<jenkins.model.JenkinsLocationConfiguration>
  <jenkinsUrl>http://$CURRENT_IP:8080/</jenkinsUrl>
</jenkins.model.JenkinsLocationConfiguration>
EOF

# Restart Jenkins to apply changes (optional)
sudo systemctl restart jenkins

echo "Updated Jenkins URL to http://$CURRENT_IP:8080 and restarted Jenkins."


# Set Jenkins URL
echo "<?xml version='1.1' encoding='UTF-8'?>
<jenkins.model.JenkinsLocationConfiguration>
  <jenkinsUrl>http://$(curl -s http://checkip.amazonaws.com):8080/</jenkinsUrl>
</jenkins.model.JenkinsLocationConfiguration>" > /var/lib/jenkins/jenkins.model.JenkinsLocationConfiguration.xml

# Restart Jenkins to apply the change
systemctl restart jenkins
