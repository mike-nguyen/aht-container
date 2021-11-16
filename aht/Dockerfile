FROM registry.fedoraproject.org/fedora:34
RUN dnf install -y git python2 https://kojipkgs.fedoraproject.org//packages/python2-pip/19.1.1/9.fc32/noarch/python2-pip-19.1.1-9.fc32.noarch.rpm
RUN pip2 install -U 'ansible<2.5' 'jmespath'
RUN useradd builder --uid 1000
WORKDIR /srv
RUN chown builder: /srv
RUN su - builder -c 'git clone https://github.com/projectatomic/atomic-host-tests.git /srv/atomic-host-tests'
USER builder
