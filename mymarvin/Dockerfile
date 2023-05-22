FROM jenkins/jenkins:latest

## skip setup wizard
ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false"

## CASC_JENKINS_CONFIG is the path to the configuration file in environment variable

COPY my_marvin.yml /var/jenkins_home/casc_configs/my_marvin.yml
ENV CASC_JENKINS_CONFIG=/var/jenkins_home/casc_configs/my_marvin.yml

COPY job_dsl.groovy /var/jenkins_home/job_dsl.groovy

## install plugins
## RUN cloudbees-folder configuration-as-code credentials github instance-identity job-dsl script-security structs role-strategy ws-cleanup --plugins "blueocean:1.25.6 docker-workflow:1.29"
RUN jenkins-plugin-cli --plugins 'configuration-as-code:latest credentials:latest github:latest instance-identity:latest job-dsl:latest script-security:latest structs:latest role-strategy:latest ws-cleanup:latest'