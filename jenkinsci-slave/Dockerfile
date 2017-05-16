FROM jenkinsci/slave

RUN mkdir /home/jenkins/.ssh

RUN wget https://s3-eu-west-1.amazonaws.com/studeal-jenkins/jenkins_known_hosts

RUN wget https://s3-eu-west-1.amazonaws.com/studeal-jenkins/jenkins_rsa

RUN wget https://s3-eu-west-1.amazonaws.com/studeal-jenkins/jenkins_rsa.pub

RUN mv jenkins_known_hosts /home/jenkins/.ssh/known_hosts

RUN mv jenkins_rsa /home/jenkins/.ssh/id_rsa

RUN mv jenkins_rsa.pub /home/jenkins/.ssh/id_rsa.pub
