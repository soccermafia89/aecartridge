FROM goldmann/f20

RUN yum install -y python-pip

RUN mkdir -p /opt/openshift && \
  groupadd -r python_app -g 433 && \
  useradd -u 431 -r -g python_app -d /opt/openshift -s /sbin/nologin -c "python app user" python_app

ADD ./prepare /opt/openshift/prepare
ADD ./launch  /opt/openshift/launch
RUN chown -R python_app:python_app /opt/openshift && chmod +x /opt/openshift/*
