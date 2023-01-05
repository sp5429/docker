FROM centos:7.9.2009
LABEL author=sp5429<sp5429@outlook.com>
RUN yum install -y \
  apr apr-util bzip2 iproute krb5-devel less libyaml \
  openssh openssh-clients openssh-server openssl \
  rsync zip libevent net-tools perl which vim initscripts
RUN groupadd gpadmin \
  && useradd gpadmin -r -m -g gpadmin \
  && echo "gpadmin" | passwd --stdin gpadmin \
  && echo "1" | passwd --stdin root

RUN sed -i 's/UsePAM yes/UsePAM no/g' /etc/ssh/sshd_config
RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key
RUN sed -i '/^session\s\+required\s\+pam_loginuid.so/s/^/#/' /etc/pam.d/sshd
RUN sed -i '/^session\s\+required\s\+pam_loginuid.so/s/^/#/' /etc/pam.d/sshd
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]