FROM jenkinsci/slave

RUN mkdir /home/jenkins/.ssh

#RUN wget https://s3-eu-west-1.amazonaws.com/studeal-jenkins/jenkins_known_hosts; exit 0

RUN wget https://s3-eu-west-1.amazonaws.com/studeal-jenkins/jenkins_rsa; exit 0

RUN wget https://s3-eu-west-1.amazonaws.com/studeal-jenkins/jenkins_rsa.pub; exit 0

RUN mv jenkins_known_hosts /home/jenkins/.ssh/known_hosts; exit 0

RUN mv jenkins_rsa /home/jenkins/.ssh/id_rsa; exit 0

RUN mv jenkins_rsa.pub /home/jenkins/.ssh/id_rsa.pub; exit 0

USER root

RUN chown jenkins:jenkins /home/jenkins/.ssh/id_rsa; exit 0

RUN chown jenkins:jenkins /home/jenkins/.ssh/id_rsa.pub; exit 0

USER jenkins

RUN chmod 600 /home/jenkins/.ssh/id_rsa; exit 0

RUN chmod 600 /home/jenkins/.ssh/id_rsa.pub; exit 0

RUN ssh-keyscan -t rsa bitbucket.org >> /home/jenkins/.ssh/known_hosts
